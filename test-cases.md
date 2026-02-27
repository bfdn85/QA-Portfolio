# Test Case Examples

## Feature: User Login

---

### Test Case 1: Successful Login with Valid Credentials

**Preconditions**
- User account exists and is active
- User is on login page

**Test Steps**
1. Enter valid email address
2. Enter valid password
3. Click Login button

**Expected Results**
- User is authenticated successfully
- User is redirected to dashboard
- User session is created

**Priority:** High  
**Type:** Functional  

---

### Test Case 2: Login with Incorrect Password

**Preconditions**
- User account exists

**Test Steps**
1. Enter valid email
2. Enter incorrect password
3. Click Login

**Expected Results**
- Error message displayed: Invalid credentials
- User remains on login page
- No session created

**Priority:** High  
**Type:** Negative  

---

### Test Case 3: Account Lock After Multiple Failed Attempts

**Test Steps**
1. Enter valid email
2. Enter incorrect password 5 times consecutively

**Expected Results**
- Account is temporarily locked
- Lockout message displayed
- Further login attempts blocked

**Priority:** High  
**Type:** Security  

---

### Test Case 4: Login with Empty Fields

**Test Steps**
1. Leave email blank
2. Leave password blank
3. Click Login

**Expected Results**
- Required field validation messages displayed
- No request sent to server

**Priority:** Medium  
**Type:** Validation  

---

### Test Case 5: Session Persistence

**Test Steps**
1. Log in successfully
2. Refresh the browser

**Expected Results**
- User remains logged in
- Session token remains valid

**Priority:** Medium  
**Type:** Functional  

---

### Test Case 6: SQL Injection Attempt in Email Field

**Test Steps**
1. Enter ' OR 1=1 -- in email field
2. Enter any password
3. Click Login

**Expected Results**
- Login fails
- Input is sanitized
- No system crash or exposure

**Priority:** High  
**Type:** Security  

---

### Test Case 7: Login Performance Under Normal Conditions

**Test Steps**
1. Enter valid credentials
2. Click Login

**Expected Results**
- Login completes within acceptable response time (e.g., < 2 seconds)

**Priority:** Medium  
**Type:** Performance  
