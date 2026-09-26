# Windows Event ID 4624 — Successful Logon Investigation

## Overview

This investigation analyzes a successful Windows logon event collected from the Windows endpoint through Wazuh.

The purpose was to understand successful authentication activity and use the Windows Logon ID to correlate related security events.

## Event Information

- Event ID: 4624
- Event Description: An account was successfully logged on
- Log Source: Windows Security Event Log
- Wazuh Agent: vedhan
- Agent ID: 002
- Channel: Security

## Investigation Findings

The investigated event showed a successful Windows logon.

Observed information included:

- Process: `C:\Windows\System32\lsass.exe`
- Subject User: `VEDHANS`
- Target Domain: `MicrosoftAccount`
- Target User: `vedhan88@outlook.com`
- Workstation: `VEDHAN`
- Target Logon ID: `0x26c0ef0`

## Analysis

Event ID 4624 records a successful authentication event.

The Logon ID is particularly useful because it can be used to associate related Windows security events with the same logon session.

The investigated event was part of normal Windows activity observed during the monitoring process.

The event was not treated as suspicious based on this event alone.

## Event Correlation

A separate Windows logon session was also investigated using Logon ID `0x26bfccb`.

That Logon ID was used to identify related security events associated with the same Windows session.

Event correlation was performed by comparing Logon ID values rather than relying only on event timestamps.

## Evidence

Relevant screenshot:

- `10-wazuh-4624-successful-logon.png`

## Conclusion

Windows Event ID 4624 was successfully collected and analyzed through Wazuh.

The investigation demonstrated how successful authentication events can provide useful information about Windows logon activity and how Logon IDs can be used as identifiers when correlating related security events.
