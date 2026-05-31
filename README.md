# WAF Policy Review Automation Tool

## Overview
A Python-based security automation tool that extracts configuration data 
from F5 BIG-IP ASM Web Application Firewall profile JSON files and 
generates structured, audit-ready PDF reports for WAF policy reviews.

## Problem Statement
Manual WAF policy reviews across multiple application profiles are 
time-consuming, error-prone, and inconsistent. This tool eliminates 
manual data collection by programmatically extracting configuration 
datapoints directly from F5 BIG-IP ASM policy JSON exports.

## What It Does
- Reads F5 BIG-IP ASM application profile configuration JSON files
- Extracts key security configuration datapoints including:
  - Blocking settings and evasion technique exceptions
  - HTTP protocol compliance status
  - IP Intelligence category configurations
  - Signature sets and staging status
  - Wildcard URL, file type, and parameter settings
  - Whitelisted IP addresses
  - Policy Builder learning mode status
- Generates a consolidated multi-page PDF audit report
- Color-coded output: Red for security violations, Green for compliant controls
- Includes sign-off blocks for Reviewer and Approver

## Business Impact
Reduced WAF compliance verification lifecycle from 30 days to 48 hours 
— a 93% improvement in audit cycle time across production application profiles.

## Technical Stack
- Python 3.x
- fpdf2 — PDF generation
- pathlib — file system operations
- json — configuration parsing

## Requirements
- pip install fpdf2
  
## Usage
```bash
python waf_policy_review.py
```
When prompted, enter the folder path containing your F5 BIG-IP ASM 
profile JSON export files.

## Output
Generates `WAF_policy_review.pdf` in the current directory containing:
- Executive cover page with purpose, disclaimer, and sign-off blocks
- One page per application profile with complete security configuration analysis

## Applicability
Designed for F5 BIG-IP ASM WAF environments. Requires application 
profile configuration exported in JSON format from F5 BIG-IP.

## Disclaimer
This tool is intended for authorized security review purposes only. 
Ensure you have appropriate authorization before reviewing WAF configurations.

## Author
Siddeshwar Marumamula  
CISSP | CISA | AWS Certified Security Specialty  
[LinkedIn](https://www.linkedin.com/in/marumamulas)
