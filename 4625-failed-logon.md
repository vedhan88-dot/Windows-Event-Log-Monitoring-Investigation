# Windows Event ID 4625 — Failed Logon Investigation

## Overview

This investigation analyzes a controlled Windows failed logon event generated on the Windows endpoint and detected through Wazuh.

The purpose of the investigation was to understand how Windows records failed authentication attempts and how the event can be monitored and analyzed through Wazuh.

## Event Information

- Event ID: 4625
- Event Description: An account failed to log on
- Log Source: Windows Security Event Log
- Wazuh Agent: vedhan
- Agent ID: 002
- Channel: Security
- Rule Description: Logon Failure - Unknown user or bad password
- Rule ID: 60122
- Rule Level: 5

## Test Method

A temporary Windows account was created for testing.

A single incorrect password was intentionally entered for the test account to generate a controlled failed authentication event.

The resulting Event ID 4625 was observed in Windows Event Viewer and subsequently detected by Wazuh.

## Investigation Findings

The event showed that the authentication attempt failed.

The event contained authentication information including:

- Authentication package: Negotiate
- Logon Type: 2
- Source IP address: 127.0.0.1
- Status: 0xC000006D
- Windows computer: vedhan
- Account information associated with the failed authentication attempt

## Analysis

Logon Type 2 represents an interactive logon attempt.

The source address `127.0.0.1` indicates that the authentication activity recorded in this event originated locally on the Windows endpoint.

The event was generated intentionally as part of a controlled test. Therefore, the event does not represent an actual unauthorized login attempt.

## Wazuh Detection

Wazuh successfully received the Windows Security Event and generated a detection for the failed logon.

The event was located through the Wazuh Threat Hunting interface by searching for Event ID 4625.

## Evidence

Relevant screenshots:

- `01-windows-event-viewer-4625.png`
- `04-wazuh-4625-results.png`
- `05-wazuh-4625-details.png`

## Conclusion

The Windows endpoint successfully generated Event ID 4625 after a controlled failed authentication attempt.

Wazuh successfully collected and displayed the event, allowing the authentication activity to be investigated and documented.

Because the failed login was intentionally generated during testing, the event was classified as a controlled and expected security event.
