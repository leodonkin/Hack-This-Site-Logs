# HackThisSite Basic Challenges Security Writeups

> [!IMPORTANT]
> ## Legal Notice
> This project documents my learning from authorised cybersecurity training environments.
> All testing was performed legally for educational purposes.

---

# Basic Level 1

## Vulnerability:
Information Disclosure

## What happened:

The website accidentally exposed information inside the page source code.

Since HTML code is downloaded by the browser, anyone viewing the website can inspect what was sent to them.

## How it could be exploited:

Someone could inspect the website code and find information that developers accidentally left behind, such as comments, hidden information, or clues about how the website works.

## What I learned:

Anything given to the browser should be considered visible.

Important information should never be stored inside public website code.

## Prevention:

Keep sensitive information on the server.

Review code before releasing websites.

---

# Basic Level 2

## Vulnerability:
Incorrect File Setup

## What happened:

The application expected a password file to exist, but it was not set up correctly.

Testing different inputs showed that the application did not properly handle the missing file.

## How it could be exploited:

Someone could discover mistakes in how the website handles missing files or errors and use that information to understand how the system works.

## What I learned:

Websites should safely handle errors instead of revealing useful information.

## Prevention:

Check files exist before using them.

Create proper error handling.

---

# Basic Level 3

## Vulnerability:
Trusting Browser Data

## What happened:

The website used hidden HTML fields to store important information.

I found that these fields could still be viewed and changed because they are sent to the user's browser.

## How it could be exploited:

Someone could inspect the website, reveal hidden fields, and change values that the website incorrectly trusts.

## What I learned:

Hidden does not mean secure.

Anything sent to the browser can be inspected.

## Prevention:

Store important information on the server.

Do not trust values controlled by users.

---

# Basic Level 6

## Vulnerability:
Weak Encryption

## What happened:

The encryption method used predictable patterns.

By testing different inputs, it was possible to understand how the encryption changed the text.

## How it could be exploited:

If an encryption system is easy to predict, someone may be able to reverse it and reveal information that should stay private.

## What I learned:

Making your own encryption systems is risky.

Strong, tested encryption methods should be used instead.

## Prevention:

Use trusted encryption libraries.

Use secure password hashing methods.

---

# Basic Level 7

## Vulnerability:
OS Command Injection

## What happened:

The website passed user input into a system command without checking it properly first.

This allowed extra instructions to be processed by the system.

## How it could be exploited:

Someone could provide unexpected input that changes what command the server runs.

Depending on the permissions of the application, this could expose files or affect the system.

## What I learned:

User input should never be trusted automatically.

## Prevention:

Check user input.

Avoid directly running system commands with user data.

Limit what permissions applications have.

---

# Basic Level 10

## Vulnerability:
Broken Access Control

## What happened:

The website trusted a value stored in the browser to decide if a user was allowed access.

## How it could be exploited:

Someone could change information stored in their browser and make the website think they have different permissions.

## What I learned:

The user controls their own browser, so websites cannot rely on it for security decisions.

## Prevention:

Check permissions on the server.

Use proper session management.
