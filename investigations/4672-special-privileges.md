# Windows Event ID 4672 — Special Privileges Investigation

## Overview

This investigation analyzes Windows Event ID 4672, which records when special privileges are assigned to a newly logged-on account.

The event was collected from the Windows endpoint through Wazuh and examined using the Wazuh Threat Hunting interface.

## Event Information

- Event ID: 4672
- Event Description: Special privileges assigned to new logon
- Log Source: Windows Security Event Log
- Wazuh Agent: vedhan
- Agent ID: 002
- Channel: Security

## Investigation Findings

The event showed that special privileges were assigned to a Windows logon session.

The privilege information included privileges such as:

- SeDebugPrivilege
- SeBackupPrivilege
- SeRestorePrivilege
- SeTakeOwnershipPrivilege
- SeLoadDriverPrivilege
- SeSystemEnvironmentPrivilege

## Logon ID Correlation

The investigated 4672 event contained the Logon ID:

`0x26bfccb`

The same Logon ID was used to correlate the activity with related Windows authentication events.

The event sequence included:

- Event ID 4624 — Successful Logon
- Event ID 4672 — Special Privileges Assigned
- Event ID 4634 — Logoff

The shared Logon ID provided a way to associate these events with the same Windows logon session.

## Analysis

Event ID 4672 can occur during legitimate administrative or privileged Windows activity.

The presence of special privileges alone does not establish malicious activity. The account, privileges, timing, and related events should be reviewed to determine whether the activity is expected.

In this project, the events were generated and investigated within a controlled Windows environment.

## Evidence

Relevant screenshots:

- `09-wazuh-4672-details.png`
- `10-wazuh-4624-successful-logon.png`
- `11-wazuh-4634-logoff.png`
- `12-wazuh-4672-logon-correlation.png`

## Conclusion

The investigation demonstrated how Event ID 4672 can be monitored through Wazuh and correlated with other Windows security events using the Logon ID.

This provided practical experience with privilege monitoring and Windows event correlation.
