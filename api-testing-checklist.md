# API Testing Checklist

## Request Validation
- Verify correct HTTP method (GET, POST, PUT, DELETE)
- Validate request headers
- Confirm authentication tokens are required and valid
- Check request payload structure and required fields

## Response Validation
- Verify correct status codes
- Validate response schema
- Confirm response time is within acceptable range
- Ensure error messages are meaningful and secure

## Functional Validation
- Verify data accuracy
- Confirm business rules are enforced
- Validate pagination and filtering
- Check idempotency where applicable

## Negative Testing
- Missing required fields
- Invalid data types
- Unauthorized requests
- Expired tokens

## Security Checks
- Ensure sensitive data is not exposed
- Validate authorization rules
- Check rate limiting behavior
