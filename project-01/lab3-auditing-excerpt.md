# Configure process creation auditing
auditpol /set /subcategory:"Process Creation" /success:enable /failure:enable

# Enable command-line capture for Event ID 4688
reg add "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System\Audit" `
    /v ProcessCreationIncludeCmdLine_Enabled `
    /t REG_DWORD `
    /d 1 `
    /f

# Verify process creation auditing
auditpol /get /subcategory:"Process Creation"

# Verify command-line logging registry setting
reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System\Audit" `
    /v ProcessCreationIncludeCmdLine_Enabled

# Force policy refresh
gpupdate /force

# Generate a test process
cmd.exe /c "echo Hello, PPID Spoofing Test"

# Query recent Event ID 4688 events
Get-WinEvent -LogName Security |
    Where-Object { $_.Id -eq 4688 } |
    Select-Object -First 5
