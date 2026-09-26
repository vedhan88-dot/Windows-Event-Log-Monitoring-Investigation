# Windows Event Log Monitoring & Investigation

## Project Overview

This project demonstrates hands-on Windows security monitoring and event investigation using Windows Event Logs and Wazuh.

The project focuses on collecting Windows security events, analyzing individual events, investigating process activity, and correlating related events using Logon IDs.

## Objectives

- Understand Windows Security Event Logs
- Monitor Windows authentication activity
- Investigate failed and successful logons
- Analyze process creation events
- Capture process command-line activity
- Investigate special privilege assignments
- Correlate related Windows security events
- Use Wazuh to centralize and analyze Windows events
- Document investigation findings and evidence

## Environment

- Windows 11 Host
- Ubuntu Wazuh Manager
- Wazuh Agent
- Wazuh Dashboard
- VirtualBox
- Windows Event Viewer
- PowerShell
- Command Prompt

## Architecture

Windows 11 Host
       |
       | Windows Security Events
       v
   Wazuh Agent
       |
       | Event Transmission
       v
 Wazuh Manager
       |
       v
 Wazuh Dashboard
       |
       v
Event Analysis & Correlation

## Windows Events Investigated

### Event ID 4624 — Successful Logon

Used to examine successful Windows authentication activity and identify the associated Logon ID.

### Event ID 4625 — Failed Logon

Used to investigate a controlled failed authentication attempt and examine authentication-related details.

### Event ID 4634 — Logoff

Used to identify when a Windows logon session ended and correlate the event using the Logon ID.

### Event ID 4672 — Special Privileges Assigned

Used to investigate Windows logon sessions that were assigned special privileges.

### Event ID 4688 — Process Creation

Used to investigate newly created processes, including process names, parent processes, process IDs, and command-line information.

## Investigation Workflow

Windows Event Generation
          |
          v
   Windows Event Viewer
          |
          v
      Wazuh Agent
          |
          v
     Wazuh Manager
          |
          v
     Wazuh Dashboard
          |
          v
      Event Analysis
          |
          v
    Event Correlation
          |
          v
 Investigation Documentation

## Key Investigation Areas

### Authentication Monitoring

Investigated successful and failed Windows authentication events using Event IDs 4624 and 4625.

### Process Monitoring

Investigated Event ID 4688 and examined process creation activity, parent processes, and command-line information.

### Privilege Monitoring

Investigated Event ID 4672 to understand special privileges assigned to a Windows logon session.

### Session Correlation

Correlated related Windows events using the Logon ID to follow activity across a Windows logon session.

## Evidence

Screenshots and investigation evidence are stored in the screenshots directory.

The project contains 12 screenshots documenting Windows Event Viewer activity, Wazuh event detection, event details, process activity, privilege assignments, and event correlation.

## Investigation Documentation

Detailed event investigations are stored in the investigations directory.

The investigation documentation covers:

- Event ID 4624 — Successful Logon
- Event ID 4625 — Failed Logon
- Event ID 4634 — Logoff
- Event ID 4672 — Special Privileges Assigned
- Event ID 4688 — Process Creation

## Repository Structure

Windows-Event-Log-Monitoring-Investigation/
│
├── investigations/
│   ├── 4624-successful-logon.md
│   ├── 4625-failed-logon.md
│   ├── 4634-logoff.md
│   ├── 4672-special-privileges.md
│   └── 4688-process-creation.md
│
├── screenshots/
│   ├── 01-windows-event-viewer-4625.png
│   ├── 02-windows-event-viewer-4688.png
│   ├── 03-wazuh-agent-active.png
│   ├── 04-wazuh-4625-results.png
│   ├── 05-wazuh-4625-details.png
│   ├── 06-wazuh-4688-results.png
│   ├── 07-wazuh-4688-process-details.png
│   ├── 08-wazuh-4688-command-line.png
│   ├── 09-wazuh-4672-details.png
│   ├── 10-wazuh-4624-successful-logon.png
│   ├── 11-wazuh-4634-logoff.png
│   └── 12-wazuh-4672-logon-correlation.png
│
└── README.md

## Tools Used

- Windows Event Viewer
- Wazuh
- Wazuh Agent
- Wazuh Manager
- Wazuh Dashboard
- PowerShell
- Command Prompt
- VirtualBox

## Project Outcome

This project provided practical experience with Windows security event monitoring, Wazuh-based event collection, process monitoring, authentication analysis, privilege monitoring, and event correlation.

The project demonstrates a practical workflow for investigating Windows security events from event generation through centralized monitoring, analysis, correlation, and documentation.

## Disclaimer

All security events and authentication activities in this project were generated and investigated in a controlled environment for educational and documentation purposes.
