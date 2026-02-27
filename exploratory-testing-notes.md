# Exploratory Testing Notes

## Feature Under Test
User Login Flow

## Objective
Explore usability, error handling, and unexpected behaviors outside predefined test cases.

## Observations

- Login form does not clearly indicate password requirements
- Error message disappears too quickly for users to read
- Password field allows copy-paste (potential security consideration)
- Page reload clears error state inconsistently

## Risks Identified

- Users may struggle with password rules
- Accessibility concerns with error message timing
- Potential security considerations around clipboard behavior

## Suggestions

- Add helper text for password requirements
- Keep error messages visible until user interaction
- Evaluate clipboard behavior based on security policy
