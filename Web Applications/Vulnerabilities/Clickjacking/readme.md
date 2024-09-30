

### **Clickjacking**

| **Aspect**                   | **Details**                                                                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Description**              | Clickjacking is a malicious technique that tricks a user into clicking on something different from what they perceive, potentially allowing an attacker to perform actions on behalf of the user without their knowledge. This often involves layering a transparent iframe over legitimate content, making it difficult for the user to see what they are actually clicking. |
| **Conditions to be Vulnerable** | - The application does not implement proper security measures like frame-busting techniques or X-Frame-Options headers. <br> - The site can be embedded in iframes by third-party websites without restriction. |
| **Where to Find**            | - Websites with sensitive actions such as payment processing, account settings, or admin functionalities. <br> - Applications that lack X-Frame-Options headers. |
| **Common Exploits**          | - Users are tricked into authorizing a payment by clicking on a hidden button. <br> - An attacker can manipulate user input in forms or change settings by making users click on disguised buttons or links. |
| **Exploitation Conditions**   | - The application can be embedded within iframes, allowing attackers to overlay their malicious content. <br> - Users have access to the vulnerable application through an unprotected URL. |
| **Example**                  | An attacker creates a page that embeds a banking site in an iframe. When the user visits this page and clicks on what they think is a button on the attacker's page, they unknowingly authorize a fund transfer on their bank account instead. |
| **Mitigation**               | - Implement the `X-Frame-Options` header with the value `DENY` or `SAMEORIGIN` to prevent the site from being embedded in iframes. <br> - Use Content Security Policy (CSP) to control which origins can frame the content. <br> - Avoid using frames for sensitive actions whenever possible. |
| **Common Payloads**          | - Clickjacking payloads typically involve JavaScript that creates an invisible iframe overlaying a legitimate site, tricking users into clicking hidden elements. |
| **Common Bypass Techniques** | 1. **Use of Transparent Overlays**: Creating transparent buttons or links that overlay legitimate content. <br> 2. **Manipulating CSS**: Using CSS to position elements in a way that confuses the user. <br> 3. **Misleading Labels**: Making buttons appear as legitimate actions while they trigger malicious behaviors. <br> 4. **Double-Click Attacks**: Requiring users to double-click on an invisible button to perform unintended actions. <br> 5. **Using Browser Features**: Exploiting browser behaviors to create deceptive experiences. <br> 6. **Social Engineering**: Convincing users to visit malicious links through phishing or other social engineering techniques. |

---

# Clickjacking Vulnerability PoC

**Description:**
This repository hosts a professional Proof of Concept (PoC) showcasing the Clickjacking vulnerability in web applications. Clickjacking represents a significant security concern, allowing unauthorized manipulation of user interactions and data access.

- Save code with .html extension.
- Change with your URL want to test.
  
```html
<html>
<title>Click Jacking</title>
<meta name="author" content="m14r41">
<head></head>
<body>
    <font color="white" size="30">
        <h2 style="font-weight: bold; color: black">Clickjacking Vulnerability Poc</h2>
        <p style="font-weight: bold; color: rgb(146, 83, 83)">This vulnerability presents a security risk, allowing for potential manipulation</br> of user interactions and unauthorized data access without user consent.</p>
        <iframe src="http://testphp.vulnweb.com/" width="70%" height="70%"></iframe>
</body>
</html>
```

---

![image](https://github.com/m14r41/Clickjacking-Poc/assets/95265573/42fd8f35-bd40-480e-87a1-fafc8392ab21)

**Features:**

- A clear title explaining the repository's purpose.
- A concise explanation of Clickjacking vulnerability.
- Inclusion of an `<iframe>` element demonstrating a common Clickjacking vector.

**By:** [m14r41](https://github.com/m14r41)
