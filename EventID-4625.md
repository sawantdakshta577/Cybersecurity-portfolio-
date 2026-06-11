# Event ID 4625 Analysis

## Alert Name

Failed Account Logon

## Event ID

4625

## Description

Event ID 4625 is generated when a logon attempt fails on a Windows system.

## Environment

* Computer Name: SOC-LAB-01
* Operating System: Windows 11
* Log Source: Windows Security Log

## Investigation

The event was identified in the Windows Security Log.

Observed Details:

* Event ID: 4625
* Logon Type: 2 (Interactive Logon)
* Account Name: USER01
* Failure Reason: Unknown user name or bad password
* Status Code: 0xC000006D
* Sub Status: 0xC000006A
* Source Address: 127.0.0.1 (Local System)
* Authentication Package: Negotiate
* Process Name: C:\Windows\System32\svchost.exe

## Analysis

Logon Type 2 indicates an interactive login attempt at the local system.

The failure reason and status codes indicate that an incorrect password was entered for the specified account. The source address 127.0.0.1 shows the request originated from the local machine.

No evidence of remote access, brute-force activity, or password spraying was identified.

## Findings

A local user entered incorrect credentials during an interactive login attempt.

The event appears consistent with normal user behavior and was successfully reproduced in a controlled lab environment.

## MITRE ATT&CK Mapping

Technique: T1110 - Brute Force (Simulation Only)

Note: In this case, the activity was a single user mistake rather than an actual brute-force attack.

## Impact

No security impact detected.

## Verdict

False Positive / Benign User Activity

## Analyst Conclusion

The failed logon event was caused by an incorrect password entered during a local interactive login attempt. The activity originated from the local host and does not indicate malicious behavior. No further action is required.
