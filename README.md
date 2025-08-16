### 🔐 EH – Netcat Shell Labs
## This repository contains a series of hands-on labs demonstrating how I use **Netcat** for:
1. Reverse Shells
2. Bind Shells
3. Shell Stabilization

These labs are designed for **educational purposes** only, using **Kali Linux** (attacker) and **Metasploitable 2** (victim) in an isolated virtual lab.

---

## 📚 Labs

### [Lab 01 – Reverse Shell](./EH-NETCAT-SHELL_01/LAB_GUIDE.md)

- Created a **reverse shell** from Metasploitable (victim) to Kali (attacker).

- ✅ Key skills: `nc -l -v -n -p` & `-e /bin/bash`

---

### [Lab 02 – Bind Shell](./EH-NETCAT-SHELL_02/LAB_GUIDE.md)

- Created a **bind shell** on the victim machine and connect from Kali.

- ✅ Key skills: `nc -lvnp` & client connections

---

### [Lab 03 – Shell Stabilization](./EH-NETCAT-SHELL_03/LAB_GUIDE.md)

- Proceeded with techniques to **stabilize unstable shells** with Python and `stty`.

- ✅ Key skills: `pty.spawn("/bin/bash")`, `export TERM=xterm`, `stty raw -echo`

---

## 🖼️ Screenshots

Placed screenshots in the `images/` folder and cehcker them here:


- [Reverse Shell Attacker] `images/lab01_reverse_attacker.png` → Reverse shell success

- [Reverse Shell Victim] `images/lab01_reverse_victim.jpg` → Reverse shell success  

- [Bind Shell] `images/lab02_bind_attacker.png` → Bind shell success  

- [ Stabilized shell] `images/lab03_stable.png` → Stabilized shell demo  

---

## ⚙️ Tools


- **Kali Linux** (Attacker)  

- **Metasploitable 2** (Victim) → [Download](https://docs.rapid7.com/metasploit/metasploitable-2/)  

Both were on the same **host-only network** inside VirtualBox/VMware.

---

## ⚠️ Disclaimer

These labs are for **educational purposes only**.  

Do not attempt on systems you do not own or have explicit permission to test.


