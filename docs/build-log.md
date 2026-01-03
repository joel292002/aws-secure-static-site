## Build Log

- Created private S3 bucket with public access blocked
- Uploaded static site files and verified AccessDenied via direct URL
- Created CloudFront distribution with OAC
- Encountered repeated AccessDenied errors
- Debugged origin and behavior configuration
- Identified CloudFront cached error responses
- Reset CloudFront distribution and redeployed cleanly
- Verified successful access via CloudFront HTTPS endpoint
