## Design Decisions

- Chose CloudFront over public S3 hosting to enforce HTTPS and add a security layer
- Kept S3 private to follow least-privilege principles
- Used Origin Access Control instead of legacy OAI
- Deferred AWS WAF to avoid unnecessary monthly cost for a demo project
- Focused on monitoring before adding additional security controls
