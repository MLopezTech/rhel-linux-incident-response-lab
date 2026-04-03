# RHEL Linux Incident Response Lab

## Overview

This project is a production-style incident response lab built on Red Hat Enterprise Linux 9.

The goal of this lab is to simulate real-world incidents that occur in Linux and cloud operations environments and to practice responding to them using a structured, operational approach.

Rather than focusing on isolated commands, each scenario is treated as a live production issue involving investigation, root cause analysis, service restoration, and clear communication.

---

## Environment

- **Operating System:** Red Hat Enterprise Linux 9
- **Platform:** VirtualBox
- **Use Case:** Production-style incident simulation
- **Focus Areas:** Linux operations, troubleshooting, service recovery, system performance, networking, and security awareness

---

## Objective

The objective of this lab is to build practical, real-world incident response skills in a Linux environment.

Each scenario is approached as if it were impacting a live system, with emphasis on:

- validating the issue
- assessing impact
- isolating the problem
- identifying root cause
- restoring service
- confirming recovery
- communicating status clearly

This mirrors how incidents are handled in real service operations and cloud environments.

---

## Incident Scenarios

### 1. SEV-1 High CPU Incident
Simulates a performance degradation scenario where CPU utilization spikes and system responsiveness is affected. Focus is placed on identifying the offending process, stabilizing the system, and validating recovery.

---

### 2. SEV-1 Web Application Outage (Service + Port + Isolation)
Simulates a web service outage where an application becomes unavailable. The investigation isolates whether the issue is related to the service, port, or system state, and restores functionality accordingly.

---

### 3. SEV-1 DNS Resolution Failure Impacting Application Connectivity
Simulates a connectivity issue where systems can reach external IPs but fail to resolve hostnames. The investigation differentiates between network and DNS failures and restores proper resolution.

---

### 4. SEV-2 Disk Space Exhaustion Causing Service Impact
Simulates a storage-related incident where disk capacity is fully consumed, impacting system behavior or service functionality. The focus is on identifying high-usage areas and safely reclaiming space.

---

### 5. SEV-2 SSH Authentication / Security Investigation
Simulates repeated failed SSH login attempts to investigate potential unauthorized access activity. The focus is on log analysis, pattern identification, and security awareness.

---

## Incident Response Approach

Each scenario follows a structured workflow similar to real production environments:

1. **Incident Trigger**  
   Issue identified via user report or system behavior

2. **Impact Assessment**  
   Determine severity and scope

3. **Investigation**  
   Use system tools, logs, and validation steps to isolate the issue

4. **Root Cause Identification**  
   Identify the underlying problem, not just the symptom

5. **Resolution**  
   Apply corrective action to restore system functionality

6. **Validation**  
   Confirm that the system is stable and functioning normally

7. **Communication**  
   Provide clear status updates as if on an incident bridge

8. **Prevention / Lessons Learned**  
   Identify improvements for future incidents

---

## Skills Demonstrated

- Linux incident response and troubleshooting
- System performance analysis (CPU, processes)
- Service management and recovery (`systemctl`)
- Log analysis (`journalctl`, system logs)
- Disk usage investigation and remediation
- Network and DNS troubleshooting
- SSH authentication and security awareness
- Root cause analysis
- Production-style incident communication
- Structured problem-solving under pressure

---

## Why This Project Matters

This project is designed to reflect how real incidents are handled in a production environment.

It demonstrates the ability to:

- approach problems methodically
- troubleshoot across multiple layers (system, service, network)
- restore services efficiently
- communicate clearly during active issues

These are critical skills for roles in Linux operations, service operations, and cloud support engineering.

---

## Interview Value

This lab directly supports answering questions such as:

- How do you troubleshoot high CPU on a Linux server?
- What steps do you take when a service is down?
- How do you handle disk space issues in production?
- How do you differentiate between network and DNS problems?
- How would you investigate suspicious SSH activity?
- How do you communicate during an active incident?

Each scenario in this repository can be used as both a technical walkthrough and a real interview example.

---

## Status

This project is actively being built with hands-on incident simulations and supporting documentation from a RHEL 9 environment.
