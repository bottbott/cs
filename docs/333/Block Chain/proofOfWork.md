---
lang: en
title: Proof of Work
viewport: width=device-width, initial-scale=1.0
---
Proof of work can be used to slow down the rate at which connections can be 
made by requiring clients to do some sort of intensive computational task. It
should not be so slow that a user would really notice, but that it would 
hinder an attacker from attacking in bulk. 

## Hash Based Proof of Work
A simple proof of work would be to find some input $ x $ that when hashed
produces 64 bits, and the 12 most significant bits are all 0s. Someone could
presumably store all the outputs for future reuse, so...

Another one would be to do something similar but hash the concentation of 
some message, $ m $, and an input $ H(m||x) $. Now the attacker couldn't use
pre-stored results when the message is changed on every request. 

## Relation to Bitcoin
Miners must produce an acceptable hash based on several different factors 
including a growing difficulty factor. 