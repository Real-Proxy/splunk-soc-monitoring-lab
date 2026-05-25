# Architecture Overview

This project simulates a mini SOC (Security Operations Center) monitoring environment using Splunk Enterprise.

The architecture focuses on collecting, parsing, analyzing, and visualizing SSH and HTTP security logs for threat detection and monitoring purposes.

---

# Workflow

```text
SSH Logs / HTTP Logs
          ↓
      Splunk Enterprise
          ↓
   Field Extraction & Parsing
          ↓
       SPL Queries
          ↓
   Dashboards & Detection
          ↓
  Security Monitoring & Analysis
```

---

# Components

## Log Sources

- SSH Logs
- HTTP Logs

## SIEM Platform

- Splunk Enterprise

## Detection Layer

Implemented using SPL (Search Processing Language).

## Visualization Layer

Custom dashboards built using Splunk visualizations.

---

# Security Monitoring Areas

## SSH Monitoring

- Failed login analysis
- Successful login tracking
- Brute-force detection
- Source-to-destination analysis

## HTTP Monitoring

- Web reconnaissance detection
- 404 scanning analysis
- DirBuster detection
- Web traffic analysis
- Targeted server analysis