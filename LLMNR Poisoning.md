used to id hosts when DNS failes
uses Username & NTLM hash of passwd
sort of a MITM, sort of a DNS poisoning attack. Def a poisoning attack. HACKER impersonates a domain and victim sends over Uname + PWD Hash mistakenly believing it is legit.


Use `Responder` tool perform this attack

`$sudo responder -I eth0 -dwPv`
d = respond to DHCP broadcast requests
w = WPAD rogue proxy server
P = force NTLM authentication 
v = verbose

Log in on victim and use Explorer to navigate to attacker IP addr.
The NTLM hash will populate in the attacker Responder instance.


Mitigations/Remediation:
-disable LLMNR & NBT-NS (disable multicast name resolution)
-Require Network Access Control
-Require strong user password (>14 chars)

