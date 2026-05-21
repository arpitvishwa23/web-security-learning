# SQL Injection - Login Bypass (PortSwigger Lab)

## Introduction
This lab demonstrates a SQL Injection vulnerability in a login form that allows an attacker to bypass authentication and log in without valid credentials.

---

## Objective
- Identify SQL Injection in login functionality  
- Bypass authentication mechanism  
- Access restricted account without password  

---

## Application Overview
The application provides a login form where users enter username and password.

---

## Login Page
![Login Page](images/lab2/2_login_page.png)

---

## Testing for Vulnerability

A normal login attempt was performed using invalid credentials.

Example:
Username: test  
Password: test  

### Observation
- Login failed  
- Indicates authentication is working normally  

![Failed Login](images/lab2/3_failed_login.png)

---

## Payload Used

Username:
administrator'--  

Password:
anything  

---

## Vulnerability Explanation

The backend query is expected to be:

SELECT * FROM users WHERE username = 'administrator' AND password = 'anything';

After injection:

SELECT * FROM users WHERE username = 'administrator'--' AND password = 'anything';

### Explanation
- `--` is a SQL comment operator  
- Everything after `--` is ignored  
- Password condition is bypassed  
- Login is successful without valid password  

---

## Result
- Successfully logged in as administrator  
- Authentication bypass achieved  

![Success Login](images/lab2/5_success_login.png)

---
## CVSS Score

- CVSS Score: 9.8 (Critical)
- Severity: Critical

### Explanation
This SQL Injection vulnerability allows attackers to:
- Bypass login authentication
- Access admin account without password
- Gain unauthorized access to the system
- Compromise application security

## Lab Solved
![Solved](images/lab2/6_lab_solved.png)

---

##1  Key Observations
- User input not sanitized  
- SQL query directly constructed  
- Authentication logic vulnerable  

---

## Mitigation Techniques
- Use parameterized queries  
- Validate user input  
- Implement secure authentication logic  
- Avoid dynamic SQL queries  

---

## Learning Outcome
- Learned login bypass using SQL Injection  
- Understood SQL comment usage (`--`)  
- Observed real-world authentication vulnerability  

---

## Screenshots

### 1. Lab Description
![Lab Description](images/lab2/1_lab_description.png)

### 2. Login Page
![Login Page](images/lab2/2_login_page.png)

### 3. Failed Login Attempt
![Failed Login](images/lab2/3_failed_login.png)

### 4. Payload Entered
![Payload](images/lab2/4_payload.png)

### 5. Successful Login
![Success](images/lab2/5_success_login.png)

### 6. Lab Solved Confirmation
![Solved](images/lab2/6_lab_solved.png)