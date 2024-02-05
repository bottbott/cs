---
lang: en
title: Hashing
viewport: width=device-width, initial-scale=1.0
---
We use hashing to produce some fixed size output of some length we chose. 
Hashes are meant to be easy to compute since we need them all the time. Their
computation time is proportional to the input to the hash function.

Hashing can be used as a checksum where the $ H(f) = c $ is passed along with
the message and the client can check on their end if $ H(f') = c $ (for some 
arbitrary file f).

## Properties
### One-way property (preimage resistance)
It's really really really hard to find the message from the hash. 
$$
\text{Very hard to find a function f such that:} \quad f(h)= m
$$

### Second preimage resistance
If I have some message, its very hard to find another message so that their
hashes are equal. 

### Collision resistance
Two hashes may result from two different messages, but it is very very very 
hard to find any two that do. 
$$
H(m_1) = H(m_2) \quad \text{is very hard to find}
$$

Modern hashing techniques are still bound by the pigeonhole principle. We have
an infinite number of messages that are bound to some expression of a hash. For
example, we have a hash that outputs a 512 bit hash. We have $ 2^{512} $ 
possible messages that we can encode, which is a lot, but there are more than 
$ 2^{512} $ message in existence and some of them will have to map to the same 
hash. 

## Basic login with a hash
```
                        # without salt
checkpass(u):           # u: username
    pc = getString()    # get password
    h = lookup(pc)      # get stored hash
    hc = H(pc)          # get the hash of the provided password
    return hc == h

                        # with salt
checkpass(u):           # u: username
    pc = getString()    # get password
    h, s = lookup(pc)   # get stored salt, hash
    hc = cat(s, H(pc))  # get the hash of the provided password, concat w/ salt
    return hc == h
```

The hash must have strong preimage resistance so that if an attacker were to 
gain access to a hash they would not be able to derive the password.

## Hashing in Signatures
Collision resistance is essentially when hashing is used to produce a tag for
signing. If this property fails, then more than one person could be a valid
sender for a signed file which would mean non-repudiation could not be 
guaranteed. 

## Salt
Salts are added to hashes to increase their complexity. This makes a brute
force attack that much less likely to succeed. The user themselves don't need
to know the salt, and it can be stored at the host side (wouldn't be effective
anymore if it was leaked). 

## Pepper
Pepper is a version of salt that is not stored. Instead it is generated from 
$ 0 \quad \text{to} \quad 2^q-1 $, (assuming q bits for the pepper) and the 
host tries out values until it finds the shared hash. It's almost like brute
forcing on the host side, and is mostly intended as an exercise to slow down
the attacker and introduce further complexity to the hash. 

## Lamport Hashes
Lamport hashes are used for one-time passwords. [More info >](password.md)