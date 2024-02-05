---
lang: en
title: Stories
viewport: width=device-width, initial-scale=1.0
---

## Unix using encryption to "hash" passwords
One of the problems with this was that they used a symmetric cipher scheme
called DES to encrypt the passwords, but DES also has a decryption function and
if the key is compromised then the attacker could access all of the passwords. 
This is a big oversight where we want something to behave as a "hashing"
function where we have preimage resistance, now it's not so hard to potentially
recover the original password once the key is broken. 

