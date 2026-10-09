**Note on the file:** `project-01/project-readback.md` is in your `Mrees213/SEC-480` repo, but only on the `module-3` branch, not `main`. That file holds your instruction read-back comparison and contains no PowerShell. The script is in the same folder as `project-01/lab3-auditing-excerpt.md`, so the analysis below covers that file.

---

## Analysis: What Windows auditing behavior does this script explicitly configure or verify?

### Configuration

**1. The script enables auditing of the "Process Creation" subcategory for both success and failure.**
Type: **Stated**
```
auditpol /set /subcategory:"Process Creation" /success:enable /failure:enable
```

**2. The script sets the registry value `ProcessCreationIncludeCmdLine_Enabled` to `1` as a `REG_DWORD`, forcing overwrite.**
Type: **Stated**
```
reg add "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System\Audit" `
    /v ProcessCreationIncludeCmdLine_Enabled `
    /t REG_DWORD `
    /d 1 `
    /f
```

**3. The purpose of that registry value is to capture command lines in Event ID 4688.**
Type: **Stated** (in a comment only)
```
# Enable command-line capture for Event ID 4688
```
Whether setting the value actually produces that effect is **Unsupported**: NO EVIDENCE. No code checks for it.

**4. The script forces a policy refresh.**
Type: **Stated**
```
# Force policy refresh
gpupdate /force
```

### Verification

**5. The script retrieves the current "Process Creation" audit setting.**
Type: **Stated**
```
# Verify process creation auditing
auditpol /get /subcategory:"Process Creation"
```

**6. The script retrieves the `ProcessCreationIncludeCmdLine_Enabled` registry value.**
Type: **Stated**
```
# Verify command-line logging registry setting
reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System\Audit" `
    /v ProcessCreationIncludeCmdLine_Enabled
```

**7. These checks only display the settings. They do not test them against expected values.**
Type: **Inferred.** Neither command is followed by a comparison, condition, or pass/fail logic. The evidence is that only these lines appear:
```
auditpol /get /subcategory:"Process Creation"
```
```
reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System\Audit" `
    /v ProcessCreationIncludeCmdLine_Enabled
```

**8. The script launches a test process.**
Type: **Stated**
```
# Generate a test process
cmd.exe /c "echo Hello, PPID Spoofing Test"
```

**9. The test process is meant to produce an event that the next query will find.**
Type: **Inferred.** This comes from the order of the commands: the test process line appears immediately before the 4688 query.
```
cmd.exe /c "echo Hello, PPID Spoofing Test"

# Query recent Event ID 4688 events
```

**10. The script queries the Security log for Event ID 4688 and returns up to five matches.**
Type: **Stated**
```
Get-WinEvent -LogName Security |
    Where-Object { $_.Id -eq 4688 } |
    Select-Object -First 5
```

**11. The five events returned are the most recent ones.**
Type: **Stated in a comment** (`# Query recent Event ID 4688 events`). The code contains no sort or time filter, so it does not establish this. **Unsupported** by code: NO EVIDENCE.

**12. The query specifically confirms the test process was logged.**
Type: **Unsupported**: NO EVIDENCE. The filter only checks `$_.Id -eq 4688`. It does not match `cmd.exe` or the echo text.

**13. The query confirms that command-line text was captured in the events.**
Type: **Unsupported**: NO EVIDENCE. No event fields or properties are selected or checked.

**14. The script performs or detects PPID spoofing.**
Type: **Unsupported**: NO EVIDENCE. The phrase appears only inside an echoed string:
```
"echo Hello, PPID Spoofing Test"
```
No code examines or alters parent process IDs.

**15. The script handles errors or checks whether commands succeeded.**
Type: **Unsupported**: NO EVIDENCE. It contains no error-handling or exit-status checks. That absence leads to the **Inferred** claim that failures would not stop or be reported by the script itself.

---

## Cannot determine from this evidence.

- Which system or Windows version the script was run on, or whether it was run at all.
- Who ran it, when, and whether it was run with sufficient privileges.
- Whether any command succeeded, and what any command output.
- Whether the audit and registry settings stayed in effect after `gpupdate /force`, or whether another policy overrides them.
- Whether any Event ID 4688 events exist or were returned.
- Whether the returned events include the `cmd.exe` test process.
- Whether the returned events contain command-line text.
- Whether `Select-Object -First 5` returns the newest events.
- Whether this is the complete script. The file name `lab3-auditing-excerpt.md` suggests it may be partial.
- How this relates to PPID spoofing beyond the echoed text.
