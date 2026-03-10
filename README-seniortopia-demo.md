
# Seniortopia Platform Architecture & Migration Demo

This repository contains an interactive architecture demonstration showing how a multi-tenant Next.js platform can be migrated safely between infrastructure accounts and scaled across many subdomains.

The demo visualizes the full platform structure including Vercel hosting, AWS services, multi-tenant routing, and migration strategy. It was created as a technical concept to illustrate how an existing SaaS platform can be transferred from an agency-owned environment to a client-owned environment without downtime.

## Demo Overview

The demo interface simulates the architecture and operational flow of the Seniortopia platform, including:

System architecture overview
Subdomain-based multi-tenant routing
Infrastructure layout across Vercel and AWS
Account migration strategy
Tenant (city) creation workflow
Platform scaling model from a few cities to dozens
Delivery and migration timeline

## Architecture Summary

Frontend: Next.js deployed on Vercel  
Routing: Edge middleware resolves tenant from the request hostname  
Backend: AWS infrastructure including RDS, S3, Lambda, SES, and CloudFront  
DNS: Wildcard subdomain configuration for multi-tenant city instances  
Data: Shared database with tenant scoped configuration

Each city runs as its own branded subdomain while sharing the same codebase.

Example subdomains:

sandiego.seniortopia.com  
denver.seniortopia.com  
phoenix.seniortopia.com  

Tenant configuration is resolved dynamically and injected into the request context at the Edge.

## Migration Strategy

The migration approach shown in the demo focuses on a safe transfer of ownership from an agency environment to a client environment.

High-level phases include:

Phase 1 – Codebase and infrastructure audit  
Phase 2 – Vercel project transfer and AWS service migration  
Phase 3 – DNS cutover and production verification  
Phase 4 – Documentation and operational handoff

Key migration operations include:

Vercel project transfer via API  
RDS snapshot and restore  
S3 bucket replication  
Environment variable and secret rotation  
DNS wildcard validation and SSL verification

The process is designed to avoid downtime by validating the new environment before traffic is switched.

## Scaling Model

The platform is designed to scale from a handful of cities to dozens without requiring code changes.

New cities are created through the admin panel which:

Creates a tenant record in the database  
Adds the subdomain to the platform  
Loads branding and configuration for the new tenant  

This allows non-technical staff to launch new city instances without developer intervention.

## Running the Demo

This project contains a standalone HTML architecture demo.

To run locally:

1. Download the repository
2. Open the file:

seniortopia-platform-demo.html

The dashboard will open directly in the browser and all sections can be explored interactively.

No build process or dependencies are required.

## Purpose

This demo was built to clearly communicate system architecture, migration approach, and scalability strategy for a multi-tenant SaaS platform.

It focuses on technical transparency and operational planning rather than marketing presentation.

## Author

Kashif Ilyas  
Senior Full Stack Engineer
