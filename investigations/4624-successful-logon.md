# Windows Event ID 4624 — Successful Logon Investigation

## Overview

This investigation analyzes a Windows successful logon event collected by Wazuh.

The purpose was to understand how Windows records successful authentication activity and how the event can be reviewed through Wazuh.

## Event Information

- Event ID: 4624
- Event Description: An account was successfully logged on
- Log Source: Windows Security Event Log
- Wazuh Agent: vedhan
- Agent ID: 002
- Channel: Security

## Investigation Findings

The Wazuh event contained successful authentication information including:

- Target username
- Target domain
- Logon Type
- Authentication information
- Workstation information
- Process information

## Analysis

Event ID 4624 represents a successful logon.

The Logon Type provides additional context about how the authentication occurred.

Successful logon events can be used together with failed logon events to understand authentication activity on a Windows endpoint.

## Wazuh Detection

Wazuh successfully collected the Windows Security Event ID 4624 from the Windows endpoint.

The event was located through the Wazuh Threat Hunting interface by searching for Event ID 4624.

## Evidence

Relevant screenshot:

- `10-wazuh-4624-successful-logon.png`

## Conclusion

The Windows endpoint successfully generated Event ID 4624 and Wazuh collected the event.

The investigation demonstrates how successful authentication activity can be reviewed and correlated with other Windows security events.
