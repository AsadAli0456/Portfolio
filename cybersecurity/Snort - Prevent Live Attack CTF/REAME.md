# TryHackMe: Snort Challenge - Live Attacks | Complete Walkthrough

🛡️ **Master Real-Time Network Defense with Snort IPS**

A comprehensive, step-by-step guide to detecting and stopping live cyber attacks using Snort's Intrusion Prevention System capabilities.


## 🎯 Challenge Overview

**Room:** [Snort Challenge - Live Attacks](https://tryhackme.com/room/snortchallenges2)  
**Difficulty:** Intermediate  
**Time Required:** 2-3 hours  
[Medium Walkthrough](https://medium.com/@aa7661538/tryhackme-snort-challenge-live-attacks-complete-step-by-step-walkthrough-ab3160e00e64)
**Focus:** Real-time attack detection and prevention

### 📖 Scenario
You're a security analyst at J&Y Enterprise, a tech-focused coffee company. Their secret "Shot4J" recipe is under attack, and you must detect and stop live cyber threats using Snort IPS.

## 🚨 Attack Scenarios Covered

### Scenario 1: SSH Brute-Force Attack
- **Target:** SSH service (Port 22)
- **Pattern:** Repetitive login attempts
- **Detection:** Traffic pattern analysis
- **Prevention:** Real-time connection blocking

### Scenario 2: Reverse Shell Attack  
- **Target:** Outbound connections (Port 4444)
- **Tool:** Metasploit framework
- **Detection:** Persistent callback analysis
- **Prevention:** Command & control blocking

## 🛠️ Skills You'll Master

### Technical Capabilities
✅ **Live Traffic Analysis** - Monitor active network connections  
✅ **Pattern Recognition** - Identify attack signatures in real-time  
✅ **IPS Rule Writing** - Create custom prevention rules  
✅ **Active Defense** - Stop attacks as they happen  
✅ **Incident Response** - Rapid threat containment  

### Tools & Commands
- **Snort Sniffer Mode**: `sudo snort -X -n 1000`
- **IPS Deployment**: `sudo snort -c /etc/snort/rules/local.rules -A full`
- **Rule Creation**: Custom reject rules for active blocking
- **Log Analysis**: Pattern identification and forensics

## 📋 Complete Solution Guide

### 🔍 Scenario 1: Brute-Force Detection

**Step 1: Capture Live Traffic**
```bash
sudo snort -X -n 1000 > scenario1.log
more scenario1.log
```

**Step 2: Identify Attack Pattern**
- Look for repetitive SSH connections to port 22
- Pattern indicates brute-force login attempts

**Step 3: Create IPS Rule**
```bash
sudo gedit /etc/snort/rules/local.rules
```
Add rule:
```
reject tcp any any <> any 22 (msg:"Drop SSH"; sid:1000001; rev:1;)
```

**Step 4: Deploy Active Defense**
```bash
sudo snort -c /etc/snort/rules/local.rules -A full
```
*Run for 1+ minute until flag appears on desktop*

**🏆 Results:**
- **Flag:** `THM{81b7fef657f8aaa6e4e200d616738254}`
- **Service:** SSH
- **Protocol/Port:** TCP/22

---

### 🔄 Scenario 2: Reverse Shell Prevention

**Step 1: Monitor Outbound Traffic**
```bash
sudo snort -X -n 1000 > scenario2.log
more scenario2.log
```

**Step 2: Detect Reverse Shell Indicators**
- Look for persistent outbound connections to port 4444
- Common Metasploit reverse shell port

**Step 3: Create Blocking Rule**
```bash
sudo gedit /etc/snort/rules/local.rules
```
Add rule:
```
reject tcp any any <> any 4444 (msg:"Drop metasploit"; sid:1000001; rev:1;)
```

**Step 4: Stop the Attack**
```bash
sudo snort -c /etc/snort/rules/local.rules -A full
```
*Run for 1+ minute until flag appears*

**🏆 Results:**
- **Flag:** `THM{0ead8c494861079b1b74ec2380d2cd24}`
- **Protocol/Port:** TCP/4444
- **Associated Tool:** Metasploit

## 🔧 Key Learning Points

### Rule Writing Essentials
- **reject**: Actively blocks traffic (vs alert which only logs)
- **tcp any any <> any PORT**: Bidirectional blocking
- **msg**: Descriptive alert message
- **sid**: Unique rule identifier

### Attack Recognition Patterns
- **Brute-Force**: Repetitive connection attempts to same service
- **Reverse Shell**: Persistent outbound connections to uncommon ports
- **Port 4444**: Default Metasploit listener port

### Real-World Applications
- **SOC Operations**: Real-time threat monitoring
- **Incident Response**: Rapid attack containment
- **Network Defense**: Automated threat prevention
- **Forensic Analysis**: Attack pattern documentation

## ⚠️ Important Notes

### Prerequisites
- Basic networking knowledge (TCP/IP, common ports)
- Linux command line familiarity
- Understanding of attack methodologies
- Completion of basic Snort room recommended

### Success Tips
- **Run IPS mode for full minute minimum** - Flag generation requires time
- **Use sudo for all network operations** - Required for packet capture
- **Analyze patterns carefully** - Look for repetitive/persistent connections
- **Test rules first** - Use `-A console` mode before deployment

## 🎓 Career Applications

### Professional Skills Gained
- **Network Security Analyst**: Real-time threat detection
- **SOC Analyst**: Incident response and monitoring
- **Cybersecurity Engineer**: Defense system implementation
- **Penetration Tester**: Understanding attack/defense dynamics

### Industry Relevance
- Enterprise network protection
- Critical infrastructure defense
- Incident response procedures
- Compliance and monitoring requirements

## 🌟 Why This Challenge Matters

### Real-World Scenarios
- **SSH Brute-Force**: Common attack vector against servers
- **Reverse Shells**: Advanced persistent threat technique
- **Active Defense**: Moving beyond detection to prevention
- **Live Analysis**: Skills needed in actual security operations

### Technical Growth
- Transition from static analysis to real-time defense
- Understanding of IPS vs IDS capabilities
- Hands-on experience with active threat mitigation
- Professional-level network security skills

## 📚 Additional Resources

- [Official Snort Documentation](https://snort.org/documents)
- [Metasploit Framework Guide](https://docs.metasploit.com/)
- [Network Security Best Practices](https://www.sans.org/network-security/)
- [TryHackMe Network Security Path](https://tryhackme.com/paths)

## 🤝 Contributing

Found an error or have improvements? Feel free to:
- Open an issue for corrections
- Suggest additional explanations
- Share alternative approaches
- Provide feedback on clarity

## ⚠️ Ethical Use Disclaimer

This walkthrough is for educational purposes only. Use these skills responsibly:
- Only in authorized environments
- Follow all legal requirements
- Respect ethical guidelines
- Practice defensive security

---

## 🏆 Challenge Summary

**Total Questions:** 6  
**Scenarios:** 2 (Brute-Force + Reverse Shell)  
**Flags Obtained:** 2  
**Skills Level:** Intermediate Network Defense  

**Ready to defend against live attacks? Let's secure those coffee recipes! ☕🛡️**

---

⭐ **Star this repo** if it helped you complete the challenge!  
🔄 **Fork it** to add your own insights!  
📢 **Share it** with fellow cybersecurity learners!

**Happy Hunting and Stay Secure!** 🔐
