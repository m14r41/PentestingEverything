## Click Jacking Vulnerability

Clickjacking, also known as a “UI redress attack”, is when an attacker uses multiple transparent or opaque layers to trick a user into clicking on a button or link on another page when they were intending to click on the top level page. Thus, the attacker is “hijacking” clicks meant for their page and routing them to another page, most likely owned by another application, domain, or both.

Using a similar technique, keystrokes can also be hijacked. With a carefully crafted combination of stylesheets, iframes, and text boxes, a user can be led to believe they are typing in the password to their email or bank account, but are instead typing into an invisible frame controlled by the attacker.


- ==POC==

```html
<pre lang="JavaScript" line="1">

<html>

<head>

<title>ClickJacking PoC</title>

</head>

ClickJacking PoC

<h2>Your Web Application Can be Mounted within an iFrame which makes it vulnerable to ClickJacking!</h2>

<iframe src="https://ADDURLHERE/" height="450" width="1000"></iframe>

</body>

</html>

</pre>
```

