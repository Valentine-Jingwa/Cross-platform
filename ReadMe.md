## How to Run this Application

- Firstly npm install
- Check that your node is up to date
  - 'node -v' and 'npm -v'
- Update you're andriod studio then
- Npm start to run you program
- Npm test if you want to check your code's validity

---

# Security Assessment and Enhancement of Totally Secure Math App

## Abstract

This document outlines a comprehensive security assessment conducted on the Totally Secure Math App, identifying various vulnerabilities, including insecure data storage, improper authentication, code injection, insufficient input validation, and insecure code practices. Following the identification of these vulnerabilities, we implemented a series of security measures aimed at mitigating the potential risks associated with each identified issue. This document details the vulnerabilities found, the measures taken to address them, and reflections on the process.

## 1. Introduction

In the realm of software development, particularly in applications handling sensitive data and user interactions, security stands as a paramount concern. The Totally Secure Math App, a React Native application designed for educational purposes, was subjected to a thorough security assessment to identify and rectify potential vulnerabilities.

## 2. Identified Vulnerabilities

### 2.1 Insecure Data Storage

**Vulnerability:** The application stores user credentials (`username` and `password`) locally without encryption, posing a significant risk of data theft.

**Potential Issues:** Malicious entities could exploit this vulnerability to gain unauthorized access to user accounts and sensitive information.

### 2.2 Improper Authentication

**Vulnerability:** The app utilizes a static array of user credentials for authentication, lacking robustness and security in verifying user identity.

**Potential Issues:** This could lead to brute-force attacks, where an attacker tries different combinations of usernames and passwords to gain access.

### 2.3 Code Injection

**Vulnerability:** The application's `Note` component uses `eval()` to process mathematical equations, introducing the risk of code injection.

**Potential Issues:** An attacker could insert malicious code as input, potentially leading to the execution of unauthorized commands or data leakage.

### 2.4 Insufficient Input Validation

**Vulnerability:** User inputs for notes and equations are not sufficiently validated, allowing for the input of malicious data.

**Potential Issues:** This could result in persistent XSS attacks if the input data is displayed elsewhere in the app or shared with other users.

### 2.5 Insecure Code Practices

**Vulnerability:** The application code contains hardcoded credentials and lacks proper error handling, making it vulnerable to various exploits.

**Potential Issues:** Hardcoded credentials can easily be discovered by inspecting the application code, and inadequate error handling could lead to information disclosure.

## 3. Implemented Security Measures

### 3.1 Secure Data Storage

Implemented encrypted storage using React Native's SecureStore for sensitive data like user credentials, replacing plaintext local storage.

### 3.2 Secure Authentication

Introduced a more secure authentication mechanism leveraging encrypted tokens and secure session management to replace the static user array.

### 3.3 Input Validation and Sanitization

Implemented rigorous input validation and sanitization for all user inputs, especially for notes and equations, to prevent injection attacks.

### 3.4 Rectification of Insecure Code Practices

Removed all hardcoded credentials, replacing them with environment variables. Enhanced error handling to prevent information leakage and ensure robustness.

## 4. Discussion

The security measures implemented are crucial for protecting against unauthorized access, data breaches, and ensuring the integrity and confidentiality of user data. By addressing the identified vulnerabilities, we enhance the application's security posture significantly.

## 5. Reflection

The process of assessing and enhancing the app's security has underscored the importance of integrating security practices into the development lifecycle from the outset. Regular security assessments, adhering to security best practices, and staying informed about the latest security threats and mitigation strategies are imperative for developing secure software.

## References

1. OWASP. (2023). _OWASP Top Ten._ [https://owasp.org/www-project-top-ten/](https://owasp.org/www-project-top-ten/)
2. React Native. (2023). _Security in React Native Applications._ [https://reactnative.dev/docs/security](https://reactnative.dev/docs/security)

---
