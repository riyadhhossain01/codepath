# Project 9 - Honeypot

Time spent: **20** hours spent in total

> Objective: Setup a honeypot and intercept some attempted attacks in the wild

## Result

- Type of Honeypot Deployed: Dionaea, Snort, Suricata, Glastopf
- Summary:
- Total Attack(s): 3861
- Total Malware(s): 1
- GIF Walkthrough: ![Live Capture](https://github.com/riyadhhossain01/codepath/blob/master/week9/Honey%20Pot.gif)
- Attack data has been added below
## Issues Faced

- First challenge I faced was when I was loading MHN admin in browser from external network. I had to modify VPN Firewall Rule of GCP to allow http traffic from external network.
- I found my sensor was detecting lots of attack but was not detecting any payload at all. So, no malware was being captured. After experimenting a while, I found port 445 needs to be accessible from outside network to be able to successfully upload a malware which was not. Then, to check for internal network, I have uploaded a malware with metaspoilt from internal network and it was captured by sensor. I couldn't figure out how to make port 445 accsible from external network.
- I also found that if i use honeypot(snort) i found that that i started recieving TOP 5 Attack Signature also payloads.
- I have also created 4 sensors wherer I allocated 4 honey pots which are Dionaea, Snort, Suricata, Glastopf. 

## Resources

- Google cloud compute engine (https://cloud.google.com/compute/)
- Pentesting framework, Metasploit (https://www.metasploit.com/)
- Network scanning tool, netmap (https://nmap.org/)
- Modern honey network (https://threatstream.github.io/mhn/)
- Gif creator, LiceCap (https://www.cockos.com/licecap/)


[Exported Data](https://github.com/riyadhhossain01/codepath/blob/master/week9/session.json)
