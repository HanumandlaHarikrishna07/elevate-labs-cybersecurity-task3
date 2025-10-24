# Cybersecurity Internship Task 3: Vulnerability Scan Report

This repository contains the findings for Task 3 of the Elevate Labs Cybersecurity Internship. The objective was to perform a basic vulnerability scan on my local PC to identify common risks.

## Tool Used

* **Tool:** Tenable Nessus Essentials
* **Target:** `localhost` (127.0.0.1)
* **Scan Type:** Basic Network Scan

## Summary of Findings

The scan identified 27 total vulnerabilities on my local machine. The summary below is based on the grouped vulnerability list:

| Severity | Count |
| :--- | :---: |
| Critical | **1** |
| High | **1** |
| Medium | **1** |
| Mixed | **4** |
| Info | **20** |

## Detailed Findings & Remediation

Here are details on the most critical vulnerabilities found during the scan and their recommended solutions.

### 1. Oracle Database Unsupported Version Detection

* **Severity:** Critical
* **Description:** According to its version, the installation of Oracle Database running on the remote host is no longer supported. Lack of support implies that no new security patches for the product will be released by the vendor. As a result, it is likely to contain security vulnerabilities.
* **Solution:** Upgrade to a version of Oracle Database that is currently supported.

### 2. Oracle TNS Listener Remote Poisoning

* **Severity:** High
* **Description:** The remote Oracle TNS listener allows service registration from a remote host. An attacker can exploit this issue to divert data from a legitimate database server or client to an attacker-specified system. Successful exploits will allow the attacker to manipulate database instances, potentially facilitating man-in-the-middle, session-hijacking, or denial of service attacks on a legitimate database server.
* **Solution:** Apply the workaround in Oracle's advisory.

### 3. SMB Signing not required

* **Severity:** Medium
* **Description:** Signing is not required on the remote SMB server. An unauthenticated, remote attacker can exploit this to conduct man-in-the-middle attacks against the SMB server.
* **Solution:** Enforce message signing in the host's configuration. On Windows, this is found in the policy setting 'Microsoft network server: Digitally sign communications (always)'.

## Screenshots

Below are screenshots of the scan dashboard and detailed results.

### Scan Dashboard
![Nessus Scan Summary]Scan dashboard.png

### Critical Vulnerability

![Critical Vulnerability]after scanning.png

### High Vulnerability

![High Vulnerability]vulnerabilties.png
