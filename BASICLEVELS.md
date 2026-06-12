# HackThisSite Basic Challenges Security Writeups
## Legal Notice
This project documents my learning from authorised cybersecurity training environments.

All testing was performed legally for educational purposes.

## Basic Level 1

### Vulnerability:

Information Disclosure

### Notes:

The first step was checking the webpage source code to understand how
the application worked.

The page contained sensitive information that should not have been
exposed client-side.

### What I learned:

Anything sent to the browser can be viewed by the user. Sensitive
information should never be stored in HTML comments or frontend code.

### Prevention:

Remove sensitive information before deployment

Keep authentication logic server-side

## Basic Level 2

### Vulnerability:

Improper File Handling

### Notes:

I tested how the application behaved when submitting empty input.

This showed that the password file was not correctly configured, which
allowed the challenge to be bypassed.

### What I learned:

Applications should correctly handle missing files and unexpected input.

### Prevention:

Validate user input

Handle errors securely

Avoid exposing backend issues to users

## Basic Level 3

### Vulnerability:

Client Side Trust Issue

### Notes:

While inspecting the HTML source, I noticed a hidden input field.

This showed that the application was relying on client side values that
could be modified by the user.

Changing the visibility of the input revealed additional information
about where the password file was located.

### What I learned:

Hidden HTML elements are not secure because users can inspect and modify
anything sent to their browser.

### Prevention:

Do not trust client side values

Validate important data server side

## Basic Level 4

### Vulnerability:

Client Side Parameter Manipulation

### Notes:

This challenge expanded on the previous one.

By reviewing the HTML, I found that the application relied on a hidden
input value for email handling.

Changing the value demonstrated why important application logic should
not be controlled from the frontend.

### What I learned:

Users have full control over client side code.

### Prevention:

Perform validation server side

Do not store important values inside hidden fields

## Basic Level 5

### Vulnerability:

Client Side Parameter Manipulation

### Notes:

This challenge used a similar concept to Level 4.

The same security issue existed where the application trusted
information controlled by the client.

### What I learned:

Repeated vulnerabilities are common when insecure coding practices are
reused.

### Prevention:

Secure coding standards

Server side validation

## Basic Level 6

### Vulnerability:

Weak Encryption Logic

### Notes:

I tested how the encryption system behaved by encrypting sample values
and looking for patterns.

After understanding how the transformation worked, I was able to reverse
the process.

### What I learned:

Custom encryption methods are usually insecure because patterns can
often be discovered.

### Prevention:

Avoid creating custom encryption

Use trusted cryptographic libraries

Use proper password hashing methods

## Basic Level 7

### Vulnerability:

OS Command Injection

### Notes:

The application used a UNIX calendar function where a user could enter a
year and receive the calendar output.

Testing showed that user input was being passed into a system command
without proper filtering.

This allowed additional commands to be interpreted by the system.

### What I learned:

Passing user input directly into system commands can allow unintended
behaviour.

### Prevention:

Validate and sanitise input

Avoid directly executing user controlled commands

Apply least privilege permissions

## Basic Level 8

### Vulnerability:

Server Side Includes (SSI) Injection

### Notes:

The application allowed SSI input to be processed by the server.

Testing showed that server side instructions could be interpreted,
exposing unintended information.

### What I learned:

Server side functionality can become dangerous when user input is not
correctly controlled.

### Prevention:

Disable unnecessary SSI functionality

Validate user input

Restrict server permissions

## Basic Level 9

### Vulnerability:

SSI Injection

### Notes:

This challenge built on the previous SSI vulnerability.

I tested how the application handled server side input and confirmed
that injected SSI instructions were still being processed.

### What I learned:

Fixing vulnerabilities requires removing the root cause, not just
blocking one specific example.

### Prevention:

Proper input handling

Disable unsafe server features

Use secure configurations

## Basic Level 10

### Vulnerability:

Broken Access Control

### Notes:

I inspected how the application handled authorization and discovered
that access control depended on a client controlled cookie value.

Changing the value demonstrated that authorization decisions should not
rely on data controlled by the user.

### What I learned:

Authentication and authorization checks must happen securely on the
server.

### Prevention:

Store authorization state server side

Validate sessions properly

Do not trust client controlled values

## Basic Level 11

### Vulnerability:

Directory Exposure / Information Disclosure

### Notes:

I used directory discovery techniques to understand the website
structure.

By investigating exposed paths and configuration files, I found
information that revealed the correct location needed to complete the
challenge.

### What I learned:

Misconfigured directories and exposed files can reveal sensitive
application information.

### Prevention:

Restrict directory access

Protect configuration files

Remove unnecessary public files

Configure server permissions correctly

## Summary

Completing these challenges helped me practise:

Reading and understanding web applications

Inspecting client side code

Understanding trust boundaries

Basic vulnerability discovery

Thinking about how issues can be fixed

These labs were completed only in authorised environments for learning
and cybersecurity research.
