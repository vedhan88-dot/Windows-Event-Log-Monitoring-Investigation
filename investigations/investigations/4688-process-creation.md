# Windows Event ID 4688 — Process Creation Investigation

## Overview

This investigation analyzes Windows Process Creation events generated on the Windows endpoint and collected by Wazuh.

The purpose was to understand how newly created processes can be monitored and investigated using Windows Event ID 4688.

## Event Information

- Event ID: 4688
- Event Description: A new process has been created
- Log Source: Windows Security Event Log
- Wazuh Agent: vedhan
- Agent ID: 002
- Channel: Security
- Rule Description: A process was created
- Rule ID: 67027
- Rule Level: 3

## Test Method

Process Creation auditing was enabled on the Windows endpoint.

Controlled commands were executed through Command Prompt to generate process creation activity.

The commands included:

```text
whoami
hostname
