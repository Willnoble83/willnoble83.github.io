---
layout: project
title: Python SMTP Server & Client
category: PythonSMTP
published: true
imagewidth: 1919
imageheight: 992
---

This project was developed as part of my second year at university. We were tasked with creating an email server and client in python that could work over a network. This was required to implement RFC 821 and some features of RFC5321.

The project has many features implemented such as Caesar Cypher encryption for network traffic, audit logging that tracks all commands issued to the server, shared mailboxes and mailing lists, personal mailboxes, a login system that uses password hashing and also has code generation for all codes required by RFC 821.

Commands implemented are: Verify (VRFY - Verifes that an email address exists in the local mailbox list), Reset (RSET - Resets the system to the state when the user first connects), HELO (Verifies the sender's domain which accepts any domain name), Extended HELO (EHLO - Same as HELO with all supported extensions), HELP (Returns a list of all available commands or information about a specific command), Login (LOGN - Login function that takes a username and password), Expand (EXPN - responds with all users in a mailing list), Delete (DELE - Deletes all emails in specified mailbox if user has access), READ (Reads emails from specified mailbox if user has access), NEXT/PREV (Navigates to next or previous email and sends to user), Return (RTRN - Returns system to login state), MAIL (Starts the mailing process, takes email address it is to be sent from), RCPT (Adds a recipent to the email), FLAG (Adds important or read flag to the email), DATA (Starts the data capturing process)

# Media

## Audit Log Creation

The function that is called to handle all entries into the audit log including handling of encryption whether it is enabled or disabled and support to be expanded to use other kinds of encryption

![Audit Log Creation - Python Code Snippet](/assets/images/projects/smtp/auditlogcreate.png)

## SMTP Code Generator

This generates corresponding readable text to go with every SMTP code that the server uses.

![SMTP Code Generator - Python Code Snippet](/assets/images/projects/smtp/codegenerator.png)

## DATA Command

This is the code that powers the data capturing process used in various different ways when combined with different commands

![SMTP DATA Command Handler - Python Code Snippet](/assets/images/projects/smtp/datacommand.png)

