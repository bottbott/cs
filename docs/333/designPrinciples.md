---
lang: en
title: Design Principles
viewport: width=device-width, initial-scale=1.0
---
## Access Control and Privilege Management
### Complete-Mediation
Whenever we are accessing objects we should verify that the proper authority to
do so exists. When we verify the authority we will need to authenticate an
identity to make sure they are who they say they are and then check their
authorization before granting access, and finally ensuring that the request has
not been tampered with. 

### Independent-Confirmation
Find a way to independently confirm the integrity of recieved information. 
Hashing is commonly used to verify file contents are what they are supposed to
be. Though you would need to trust that the listed hash hasn't been tampered
with. 
### Least-Privilege
Give as little access as possible. Only what is required to carry out the users
tasks.

### Safe-Defaults
Create good, safe default settings, so that when things fail - they fail in a
way that leaves the system in a secure state. 
### Trust-Anchor-Justification
Justify why you are trusting anchors of trust like a certificate authority. 
They represent the foundation of what you are building on and you should be
confident that they can be trusted.

### Verify-First
Make sure they are who they say they are before you do anything.


## User Interaction and Expectations
### Least-Surprise
Design your user interactions in line with what the user might expect. You want
to avoid building a system that relies on experts where ordinary users might
make a mistake using it. 

### User-Buy-In
Build something the user will want to use. We want to encourage them to use it,
so that they don't try to bypass it.

## System Design
### Design-For-Evolution
Build a system that can grow with new crypto algorithms for encyryption or
hashing. Build in automated updates to ensure that deployments maintain 
alignment with new releases and fixes. 

### Isolated-Compartments
Similar to modular design, we design the product such that the components are
as isolated as possible to reduce any failure in one of them from causing
failures in the other components. 

### Modular-Design
Build modular systems where access is distributed across it and avoid 
consolidating access into large singular monolithic applications where a breach
would give full access.

### Open-Design
Systems that have some openness to them mean that vulrabilities can be 
identified sooner, and that we don't overly rely on our own secret scheming to
protect us. We have robust code that has been socially reviewed and evolved.

Pairs with [**Time Tested Tools**](#time-tested-tools)
### Security-By-Design
Think about security from the beginning so that you're not playing catch up
later on.
### Simplicity-and-Necessity
Keep it simple stupid. Reducing complexity helps minimize attack surface. This
often conflicts with the desire to build big large piece of software. 
### Small-Trusted-Bases
Avoid depending on complex larger codebases. A smaller size will be easier to 
analyze for security and ensure that you aren't majorly open to attack.

We could think of the bases here as support areas that your application 
interacts with, and if they are overly large and complicated it will be 
difficult to decide they are safe to interact with.

### Time-Tested-Tools
Use tools that you and the community at large trust. They have been vetted
better than newer, cutting edge tech that may have overlooked design flaws.

## Defense Design
### Defense-In-Depth
We want to avoid single points of failure, and try to by providing defense in
multiple layers as back up. Any one piece that is weak should be improved since
attackers will target the weakest link. 

Layers provide backup for human errors in design, or some defenses that were 
more easy to bypass than expected. 
### Datatype-Validation
Be sure that you're receiving what you expect to receiving and check for that
to be true.

**Watch out** for code injection or command injection attacks. 
### Evidence-Production
Leave a bread crumb trail. The more data that you have, the better you can 
analyze an attack and repair the problem.

### Relucant-Allocation
Be cautious to allow full access to any visitor. This is often about preventing
denial of service attacks that would occur if unmitigated access is allowed. 

### Remnant-Removal
Clean up your garbage in case you kept any secrets in there. 

### Request-Response-Integrity
When something has been requested, make sure that the response matches what is
expected to have arrived based on the request. Designs should ensure that 
transactions or protocols have integrity checks built in so the contents of any
part of the chain of communication is in question.

### Sufficient-Work-Factor
There may be parts of your system that you want the user to do a certain amount
of work before allowing them access. This prevents a bad actor from trying to
brute force their way into the system through that access point.














