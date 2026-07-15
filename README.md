# Windows Security Log Investigation

This project demonstrates a basic Security Operations Center (SOC) investigation using Windows Security Event Logs. The objective is to analyze authentication and privilege-related activities, reconstruct event timelines, identify notable security events, and document investigation findings based on Windows Security auditing.

---

## Project Objectives

- Analyze Windows Security Event Logs (.evtx)
- Investigate authentication and privilege-related activities
- Correlate related Windows security events
- Reconstruct security event timelines
- Identify normal and potentially suspicious behaviors
- Produce a professional investigation report

---

## Investigation Scope

This investigation focuses exclusively on **Windows Security Logs** collected from a Windows 11 workstation.

### Analyzed Security Events

| Event ID | Description                              | Purpose                                    |
|----------|------------------------------------------|--------------------------------------------|
| 4624     | Successful Logon                         | Analyze authentication activities          |
| 4672     | Special Privileges Assigned to New Logon | Identify privileged logons                 |
| 4798     | User Group Membership Enumeration        | Review local group enumeration activities  |
| 5058     | Cryptographic Key File Operation         | Analyze cryptographic key management       |
| 5059     | Cryptographic Key Migration              | Review key migration operations            |
| 5061     | Cryptographic Operation                  | Analyze cryptographic service activities   |
| 5379     | Credential Manager Accessed              | Review credential access behavior          |

---

## Investigation Methodology

1. Export Windows Security Event Logs (.evtx)
2. Identify frequently occurring security events
3. Review Microsoft event descriptions
4. Correlate related security events
5. Reconstruct event timelines
6. Validate investigation findings
7. Produce the final investigation report

---

## Project Structure

```text
windows-security-log-investigation/
│
├── data/
│   └── raw/
│       └── Security.evtx
│
├── report/
│   ├── Investigation Report.pdf
│   └── Investigation Report.docx
│
├── images/
│   ├── timeline-Reconstruction-1.png
│   ├── timeline-Reconstruction-2.png
│   └── timeline-Reconstruction-3.png
│   └── Security Logs.png
│
└── README.md
```

---

## Investigation Workflow

```text
Windows Security Log (.evtx)
            │
            ▼
     Event Identification
            │
            ▼
      Event Correlation
            │
            ▼
 Timeline Reconstruction
            │
            ▼
    Security Assessment
            │
            ▼
 Investigation Findings
            │
            ▼
   Investigation Report
```

---

## Findings Summary

| Finding | Status |
|---------|--------|
| Normal Authentication Activity | Confirmed – Expected Behavior |
| Privileged Logon Activity | Confirmed – Expected Behavior |
| Credential Manager Access | Likely Normal |
| User Group Membership Enumeration | Likely Normal |
| Cryptographic Key Management Activities | Needs Verification |

---

## Skills Demonstrated

- Windows Event Log Analysis
- Security Event Investigation
- Authentication Analysis
- Privilege Analysis
- Timeline Reconstruction
- Event Correlation
- Security Documentation
- Technical Reporting

---

## Tools

- Windows Event Viewer
- Microsoft Word
- PowerShell
- Git & GitHub

---

## Report Contents

- Executive Summary
- Investigation Objective
- Environment Information
- Data Collection
- Investigation Methodology
- Event Analysis
- Timeline Reconstruction
- Investigation Findings
- Security Recommendations

---

## Notes

- This project focuses exclusively on **Windows Security Event Logs**.
- The investigation demonstrates an entry-level SOC investigation workflow using native Windows auditing.
- Event interpretations are based on Microsoft Windows Security auditing behavior and timeline correlation.
- The objective is to practice log analysis, event correlation, and technical documentation rather than perform a complete enterprise incident response.

---

## Future Improvements

- Enable Process Creation Auditing (Event ID 4688)
- Analyze Failed Logons (4625)
- Add MITRE ATT&CK Mapping
- Develop Sigma Detection Rules
- Integrate Sysmon Event Logs
- Visualize timelines using Power BI
- Perform automated log parsing with PowerShell

---
---

## Investigation Limitations

This investigation was conducted using Windows Security Event Logs collected from a single Windows 11 workstation. The analysis provides visibility into authentication, privilege assignment, credential access, and cryptographic activities; however, several limitations should be considered:

- Only Windows Security Event Logs were analyzed.
- Process creation events (Event ID 4688) were unavailable, preventing direct attribution of activities to executable processes.
- Network-related events and endpoint telemetry were outside the scope of this investigation.
- Event interpretation relied on timeline reconstruction and event correlation rather than endpoint forensic artifacts.
- Some security events, particularly cryptographic operations, provide limited context without additional provider, process, or application information.
- The investigation assessed observable behaviors within the available log data and cannot conclusively determine malicious intent without additional evidence.

---

## Potential Improvements

The investigation can be extended by incorporating additional telemetry and detection capabilities, including:

- Enable Process Creation Auditing (Event ID 4688) to improve process attribution.
- Integrate Sysmon logs for enhanced process, network, and file activity visibility.
- Correlate Windows Security Logs with System, Defender, and PowerShell Operational logs.
- Develop Sigma detection rules based on identified event patterns.
- Perform automated log parsing and correlation using PowerShell or Python.
- Visualize authentication timelines and event relationships using Power BI or Grafana.
- Map investigation findings to the MITRE ATT&CK framework.
- Centralize log collection using a SIEM platform for continuous monitoring and alerting.
- Expand the investigation to include account creation, privilege changes, failed authentication, and lateral movement scenarios.

---

## License

This project is intended for educational and portfolio purposes.
