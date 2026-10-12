# Security Audit Report

## The Principle of Least Privilege (PoLP)

The Principle of Least Privilege means giving a user, process, or service only the minimum access it needs to do its job, and nothing more. For cloud user accounts, this matters because if an account is ever compromised, limiting what it can access limits the damage an attacker can do — an account that only needs read access to one bucket should never also have admin rights over the entire infrastructure.

## Attack Surface

Attack surface refers to the total number of points where an unauthorized user could try to enter or extract data from a system. Applied to a virtual machine, this includes every open network port, running service, installed software, and user account on that machine — the more of these that are active and exposed, the more opportunities an attacker has to find a weakness.

## Default Deny Policy

A default deny policy blocks all incoming traffic by default and only allows specific, explicitly approved connections through. This is safer than trying to block known hackers individually because attackers are constantly changing IP addresses and techniques, making a blocklist impossible to keep complete — a default deny policy instead assumes everything is untrusted unless proven otherwise, which closes off every unknown threat automatically.
