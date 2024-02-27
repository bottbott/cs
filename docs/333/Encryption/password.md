---
lang: en
title: Password
viewport: width=device-width, initial-scale=1.0
---
Authenticating is about trying to prove who you are. This is typically 
accomplished by relying on something that the user owns or something that
the user knows. Commonly what the user knows is a password. 

There are some problems with passwords. They are susceptible to eavesdropping 
where an attacker may be able to learn them, and the are subject to replay
where the attacker may be able to continually access the system after the
password has become known. Changing passwords frequently can help minimize this
threat (although that doesn't minimize the amount of damage if a breach 
occurs).

## One-Time Passwords
These passwords may be produced ahead of time and given to the user so that
they can authenticate into the system. This may look like the host generating
a list of passwords, printing them out, and the user going through the list
one by one. The host removing the password from the system as it is used.

### Lamport Hashing
The system will precompute a series of hashes as one-time passwords based on
a users provided password. 

$$
\begin{align*}
h_1 = H(p), h_2 = H(h_1), h_3 = H(h_2), h_4 = H(h_3), ..., h_k = H(h_{k-1}) \\
\text{collection of tuples} <k-1, h_{k-1}>, <k-2, h_{k-2}>, ..., <3, h_3>, <2, h_2>, <1, h_1>
\end{align*}
$$

This list is then provided to the user in reverse order. As the user provides
them to the host they are removed from the system. The user is not given 
\( <k, h_k> \), it is stored on the host and when the user sends 
\( <k-1, h_{k-1}> \) the host will hash it to then compare against \( h_k \). 
When it matches, the host will then store the hash that the user sent and 
decrement its counter.
