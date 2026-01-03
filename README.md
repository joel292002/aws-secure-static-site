# Secure Static Website on AWS (S3 + CloudFront)

## Overview
This project demonstrates how to host a secure, scalable static website on AWS using a private S3 bucket served through Amazon CloudFront.

The design follows production best practices:
- No public access to S3
- CloudFront as the only public entry point
- HTTPS enforced by default
- Global content delivery
- Cost-aware architecture

Live demo:
https://<your-cloudfront-domain>.cloudfront.net

---

## Architecture
User → CloudFront (HTTPS) → Private S3 Bucket

CloudFront uses Origin Access Control (OAC) to securely access S3 content while keeping the bucket private.

---

## Problem Statement
Static websites are often hosted using public S3 buckets, which exposes storage directly to the internet and bypasses security and monitoring layers.

This project solves:
- Secure content delivery without public storage
- Global low-latency access
- Least-privilege access to storage
- Visibility into traffic and errors
- Minimal operational cost

---

## AWS Services Used
- Amazon S3 (private object storage)
- Amazon CloudFront (CDN + HTTPS)
- AWS IAM (Origin Access Control)
- Amazon CloudWatch (metrics & monitoring)

---

## Security Design
- S3 bucket blocks all public access
- CloudFront is the only allowed reader via OAC
- HTTPS enforced at the CDN level
- AWS Shield Standard enabled by default
- AWS WAF intentionally deferred to avoid unnecessary cost

---

## Monitoring & Observability
- Used CloudFront metrics in CloudWatch:
  - Request count
  - 4xx error rate
  - 5xx error rate
  - Data transfer
- Verified origin health through zero 5xx errors
- Reviewed costs using AWS Cost Explorer

---

## Challenges & Learnings
- Debugged repeated 403 AccessDenied errors during CloudFront setup
- Learned that CloudFront aggressively caches error responses
- Discovered how origin and behavior configuration order matters
- Reset infrastructure after identifying configuration drift
- Gained hands-on understanding of AWS billing and lifecycle controls

---

## Result
A production-style static website architecture that is:
- Secure by default
- Globally distributed
- Low-cost
- Observable and debuggable

This project reflects real-world cloud engineering practices rather than tutorial-based deployment.

