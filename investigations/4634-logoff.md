# Windows Event ID 4634 — Logoff Investigation

## Overview

This investigation analyzes Windows Event ID 4634, which records when a Windows logon session is logged off.

The event was collected from the Windows endpoint through Wazuh and examined using the Wazuh Threat Hunting interface.

## Event Information

- Event ID: 4634
- Event Description: An account was logged off
- Log Source: Windows Security Event Log
- Wazuh Agent: vedhan
- Agent ID: 002
- Channel: Security
- Computer: vedhan
- User: vedha
- Logon Type: 7
- Target Logon ID: `0x26bfccb`

## Investigation Findings

The event showed that the Windows logon session identified by Logon ID `0x26bfccb` ended.

## Event Correlation

The Target Logon ID in the 4634 event was:

`0x26bfccb`

The investigated Event ID 4672 contained the same Logon ID:

`0x26bfccb`

This shared Logon ID provides a direct correlation between the special-privilege assignment event and the later logoff event.

A separate Event ID 4624 successful logon event investigated in this project had Target Logon ID `0x26c0ef0`, so it was not treated as part of this specific 4672/4634 correlation.

## Analysis

Event ID 4634 is useful for understanding when a Windows logon session ends.

When combined with other Windows security events and the Logon ID, it can help reconstruct activity associated with a particular session.

In this project, the event was used to demonstrate Windows session correlation rather than to indicate suspicious behavior.

## Evidence

Relevant screenshots:

- `11-wazuh-4634-logoff.png`
- `12-wazuh-4672-logon-correlation.png`

## Conclusion

The Windows endpoint generated Event ID 4634 and Wazuh successfully collected the event.

The shared Logon ID `0x26bfccb` correlated the logoff event with the investigated Event ID 4672 special-privilege event.

This demonstrated how Windows security events can be connected to understand activity associated with a logon session.
