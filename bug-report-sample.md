# Bug Report Sample

## Title
Login button remains disabled after entering valid credentials

## ID
BUG-001

## Severity
High

## Priority
High

## Environment
- Browser: Chrome 121
- OS: Windows 11
- Environment: Staging

## Preconditions
User is on login page with valid account

## Steps to Reproduce
1. Navigate to login page
2. Enter valid email address
3. Enter valid password
4. Observe login button state

## Actual Result
Login button remains disabled and user cannot proceed

## Expected Result
Login button should become enabled once valid credentials are entered

## Frequency
100% reproducible

## Impact
Users cannot log in, blocking access to the application

## Root Cause (Hypothesis)
Frontend validation state not updating after input change

## Attachments
- Screenshot showing disabled button
- Console log (if available)

## Notes
Issue started after latest UI validation update
