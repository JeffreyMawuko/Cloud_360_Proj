# Cloud_360_Proj
Smart System Solution SecOps Project for Cloud CVEs

# CloudGuard360-DB
Secure, productized vulnerability intelligence microservice for **RM Smart System Solutions**.  
Ingests CVE feeds, normalizes to Postgres, matches against CycloneDX SBOMs, and exposes a REST API for policy gates.

## Calling API
curl 'http://{changeservername}:8080/v1/cves?q=openssl&min_score=7.0'
CVE Reports: https://openssl-library.org/news/vulnerabilities/index.html 
 
## Quick start (Docker)

## Script Injection Attacks: Checking Script Injection Attacks

A script injection attack can occur directly within a workflow's inline script. 
In the following example, an action uses an expression to test the validity of a pull request title, but also adds the risk of script injection:

<img width="706" height="224" alt="Screen Shot 2025-08-28 at 9 53 48 AM" src="https://github.com/user-attachments/assets/da115886-e788-423d-b290-ae0edc3826d8" />


```bash
docker compose up -d
# API: http://localhost:8080/docs

Components

/api — FastAPI service to query CVEs, packages, and policy gates.
/db — Postgres schema & migrations.
/etl — Feed ingesters (NVD JSON 2.0) and loaders.
/sbom_matcher — CycloneDX SBOM parsing & PURL-based matching.
/policy — YAML policy gates for CI (fail on CVSS, KEV, or exploit maturity).
/data — Structure for year/vendor separated CVE files + samples.
Data sources (configure in configs/config.yaml)
NVD JSON 2.0 (optional API key)
CISA KEV catalog (optional)
GitHub Security Advisories (optional, via token)
(Scripts provided; you must supply your own keys/tokens and comply with terms of use.).

