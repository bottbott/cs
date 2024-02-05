---
lang: en
title: Security Concepts
viewport: width=device-width, initial-scale=1.0
---
The acronym **CIA** stands for *confidentiality*, *integrity*, and 
*availability*. 

!!! note inline end
    Messages may be data, code and the whole computation device as a whole.

**Confidential**: we only want the people that we want to to be able to read our
messages. May apply to things that are at rest like storage, or things that are
in motion like network traffic. We are concerned with the ability authenticate
and have the user be someone we can trust, the ability to authorize and grant
them only the necessary privileges, and to create privacy so that outside 
actors can't eavesdrop on communication.

**Integrity**: we want to insure that our messages haven't been tampered with. We
use things like *cryptographic checksums* to help ensure that the contents of 
files are what we expect them to be. We want messages to be correct and know
that they are from a certain source. We want to know our messages were received
and we want to have some confidence on the flow of transactions. 

**Availability**: the message is available when needed. Includes protection against 
*denial of service* attacks. We want to ensure our service uninterupted and we
want to design fairness so that the access to the system is equally 
distributed.

