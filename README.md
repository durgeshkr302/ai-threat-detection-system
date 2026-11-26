# AI Based Threat Detection and Prevention System

This repository contains the system design and project documentation for an AI driven threat detection and prevention platform built for a mid sized enterprise environment. The goal of this design is to detect modern cyber attacks early, reduce alert fatigue for security analysts, and provide clear explanations for every security alert.

## Overview

Traditional rule and signature based security tools often struggle against modified attacks, insider threats, and zero day exploits. This project proposes a hybrid detection pipeline that combines supervised machine learning for known attack patterns with unsupervised anomaly detection for unusual user and network behavior.

## Key Threats Covered

1. Phishing and Social Engineering: Detecting deceptive emails, malicious links, and sender spoofing using text and metadata features.
2. Ransomware and Malware Execution: Identifying abnormal file encryption spikes, suspicious process trees, and high file entropy on endpoints.
3. Insider Threats and Account Takeover: Spotting unusual login locations, off hours access, and sudden spikes in data downloads.
4. Credential Stuffing and Brute Force Attacks: Monitoring rapid failed login attempts and distributed authentication anomalies.
5. Network Intrusion and DDoS Activity: Analyzing abnormal traffic volume, unusual port scanning, and suspicious outbound connections.

## System Architecture

The end to end pipeline works across five main stages:

1. Data Ingestion: Collects telemetry from authentication logs, email gateways, network flow records, and endpoint agents.
2. Feature Engineering: Extracts meaningful behavioral and statistical features such as login time deviation, failed attempt velocity, file entropy, and domain age.
3. Dual Detection Engine: Uses supervised classification models for known threat signatures and unsupervised anomaly detection models to flag unknown behavioral outliers.
4. Explainable AI Layer: Uses SHAP based feature attribution to translate complex model scores into plain English reasons for security analysts and managers.
5. Tiered Response: Routes medium risk alerts to analysts for verification while triggering automated containment actions for confirmed high severity threats.

## Security, Robustness, and Ethics

* Adversarial Defense: Protects the models against evasion and data poisoning through input sanitization, feature validation, adversarial training, and baseline drift checks.
* Explainability: Ensures every high priority alert displays the top contributing factors so analysts can verify why an event was flagged.
* Privacy and Fairness: Limits monitoring to security relevant metadata, avoids intrusive personal tracking, and keeps human analysts in the loop before taking permanent account actions.

## Repository Contents

* Project Documentation PDF: Complete system design report covering threat modeling, architecture, feature engineering, adversarial defense, XAI, and governance.
* System Architecture Diagram: Visual overview of the end to end detection and response pipeline.
* Adversarial Defense Diagram: Visual breakdown of evasion and poisoning threats alongside mitigation controls.
