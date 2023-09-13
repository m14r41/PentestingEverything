## Phishing Penetration Testing Checklist

- [ ] **Reconnaissance and Information Gathering:**
   - **Tools:** 
     - [OSINT Framework](https://osintframework.com/)
     - [Shodan](https://www.shodan.io/)
     - WHOIS lookup.
   - **Commands:** 
     - WHOIS Lookup: `whois target.com`

- [ ] **Phishing Payload Creation:**
   - **Tools:** 
     - [GoPhish](https://getgophish.com/)
     - [Social-Engineer Toolkit (SET)](https://github.com/trustedsec/social-engineer-toolkit).
   - **Commands:** 
     - Start GoPhish: `gophish`
     - Launch SET: `setoolkit`

- [ ] **Email Spoofing and Crafting:**
   - **Tools:** Email spoofing tools, email client.
   - **Commands:** 
     - Use your preferred email client to craft and send phishing emails.

- [ ] **Domain Spoofing:**
   - **Tools:** Domain registration services.
   - **Commands:** 
     - Register domains similar to the target organization's domain.

- [ ] **Sending Phishing Emails:**
   - **Tools:** 
     - [GoPhish](https://getgophish.com/)
     - [SET](https://github.com/trustedsec/social-engineer-toolkit)
     - SMTP servers.
   - **Commands:** 
     - Use GoPhish for campaign management: `gophish`

- [ ] **Credential Harvesting:**
   - **Tools:** 
     - [GoPhish](https://getgophish.com/)
     - Custom phishing pages.
   - **Commands:** 
     - Create and host phishing landing pages.

- [ ] **Reporting and Analysis:**
   - **Tools:** 
     - [GoPhish](https://getgophish.com/)
     - Email clients.
     - [Wireshark](https://www.wireshark.org/).
   - **Commands:** 
     - Monitor campaigns with GoPhish: `gophish`
     - Analyze captured data with Wireshark: `wireshark`

- [ ] **Advanced Techniques:**
   - **Tools and Frameworks:** 
     - [Evilginx2](https://github.com/kgretzky/evilginx2): Advanced phishing with 2FA bypass.
     - [King Phisher](https://github.com/securestate/king-phisher): Phishing campaign toolkit.
     - [Phishery](https://github.com/ryhanson/phishery): URL-based phishing toolkit.
   - **Commands:** 
     - Launch Evilginx2: `evilginx2`
     - Use King Phisher: `king-phisher`

- [ ] **Password Cracking:**
   - **Tools:** 
     - [Hashcat](https://hashcat.net/hashcat/): Password cracking tool.
   - **Commands:** 
     - Use Hashcat: `hashcat`

- [ ] **Post-Exploitation:**
   - **Tools and Frameworks:** 
     - [Empire](https://github.com/BC-SECURITY/Empire): Post-exploitation framework.
     - [Metasploit](https://www.metasploitunleashed.com/): Penetration testing framework.
   - **Commands:** 
     - Launch Empire: `empire`
     - Use Metasploit: `msfconsole`
