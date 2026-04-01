# SEV-1 High CPU Causing System Degradation

## Scenario

This scenario simulates a production-style performance incident on a Red Hat Enterprise Linux 9 server.

The system becomes slow and unresponsive due to abnormal CPU consumption. The objective is to validate the reported degradation, identify the process responsible for the resource spike, restore system stability, and confirm recovery using a structured incident response approach.

---

## Environment

- **Operating System:** Red Hat Enterprise Linux 9
- **Platform:** VirtualBox
- **Incident Type:** Performance Degradation
- **Severity:** SEV-1

---

## Incident Trigger

A user report or monitoring alert indicates that the Linux host is responding slowly and overall performance has degraded.

---

## Initial Symptoms

- system slowdown
- delayed terminal response
- high CPU usage
- potential service impact due to resource saturation

---

## Impact Assessment

Because CPU saturation can affect the responsiveness of the entire host and any services running on it, this incident is treated as SEV-1 until system stability is restored and the offending process is identified.

---

## Investigation Strategy

The investigation began by validating the reported issue using system load and real-time CPU monitoring tools.

After confirming CPU saturation, processes were analyzed to identify the top CPU consumers. The focus was to determine whether the activity was expected or abnormal before taking corrective action.

---

## Commands Used

``` bash
uptime
top
ps aux --sort=-%cpu | head

yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &

uptime
top
ps aux --sort=-%cpu | head

pkill yes

top
ps aux --sort=-%cpu | head
```
---
## Findings

System load and CPU utilization were significantly elevated during the incident window. Real-time monitoring using top confirmed sustained high CPU usage across multiple cores.

Process analysis using ps aux --sort=-%cpu revealed multiple yes processes consuming nearly all available CPU resources. These processes were not associated with any legitimate system workload and were identified as the source of the degradation.


## Root Cause

The incident was caused by multiple CPU-intensive background processes (yes > /dev/null &) consuming excessive processor resources and saturating the CPU.

This resulted in reduced system responsiveness and overall performance degradation.

## Resolution

The CPU-intensive yes processes were terminated using pkill yes, which immediately stopped the runaway workload and freed CPU resources.

This action restored normal system performance.

Validation

Post-remediation checks using top and ps aux --sort=-%cpu confirmed that CPU usage returned to normal levels.

The offending processes were no longer present, and system responsiveness was restored to baseline conditions.

## Bridge Call / Status Update

"Performance degradation on the affected RHEL 9 host was traced to CPU saturation caused by runaway processes. The processes have been terminated, system performance has stabilized, and validation confirms the host has returned to normal operation."

## Lessons Learned
establish CPU alert thresholds for early detection
baseline normal system performance for comparison
quickly identify abnormal processes during triage
validate system state after remediation before closing incident
Skills Demonstrated
Linux performance troubleshooting
CPU and system load analysis
process investigation and identification
incident triage and prioritization
root cause analysis
remediation and service restoration
post-incident validation
production-style communication

## Screenshot Evidence

### Baseline

![uptime command baseline](screenshots/Uptime1.png)




### During Incident






### After Fix



