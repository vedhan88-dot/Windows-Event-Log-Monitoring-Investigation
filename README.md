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

- Windows 11
- Ubuntu
- Wazuh Manager
- Wazuh Agent
- Wazuh Dashboard
- VirtualBox
- Windows Event Viewer
- PowerShell
- Command Prompt

## Architecture

Windows 11 Host
        |
        | Windows Event Logs
        |
   Wazuh Agent
        |
        | Event Transmission
        |
   Wazuh Manager
        |
        |
   Wazuh Dashboard
        |
        |
Event Investigation & Correlation

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

Investigated Event ID 4688 and examined process creation activity and command-line information.

### Privilege Monitoring

Investigated Event ID 4672 to understand special privileges assigned to a Windows logon session.

### Event Correlation

Correlated related Windows events using the Logon ID to follow activity across a Windows logon session.

## Evidence

Screenshots and investigation evidence are stored in the `screenshots` directory.

## Investigation Documentation

Detailed event investigations are stored in the `investigations` directory.

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

The project demonstrates a practical workflow for investigating Windows security events from event generation through centralized monitoring and documentation.
