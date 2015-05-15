<html>
<head>
<META http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>ZAP Scanning Report</title>
</head>
<body text="#000000">
<p>
<strong>ZAP Scanning Report</strong>
</p>
<p>

</p>
<p>
<strong>Summary of Alerts</strong>
</p>
<table width="45%" border="0">
<tr bgcolor="#666666">
<td width="45%" height="24"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Risk 
      Level</font></strong></td><td width="55%" align="center"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Number 
      of Alerts</font></strong></td>
</tr>
<tr bgcolor="#e8e8e8">
<td><font size="2" face="Arial, Helvetica, sans-serif"><a href="#high">High</a></font></td><td align="center"><font size="2" face="Arial, Helvetica, sans-serif">3</font></td>
</tr>
<tr bgcolor="#e8e8e8">
<td><font size="2" face="Arial, Helvetica, sans-serif"><a href="#medium">Medium</a></font></td><td align="center"><font size="2" face="Arial, Helvetica, sans-serif">5</font></td>
</tr>
<tr bgcolor="#e8e8e8">
<td><font size="2" face="Arial, Helvetica, sans-serif"><a href="#low">Low</a></font></td><td align="center"><font size="2" face="Arial, Helvetica, sans-serif">60</font></td>
</tr>
<tr bgcolor="#e8e8e8">
<td><font size="2" face="Arial, Helvetica, sans-serif"><a href="#info">Informational</a></font></td><td align="center"><font size="2" face="Arial, Helvetica, sans-serif">26</font></td>
</tr>
</table>
<p></p>
<p></p>
<p>
<strong>Alert Detail</strong>
</p>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="red" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="high"></a>High (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Cross Site Scripting (Reflected)</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Cross-site Scripting (XSS) is an attack technique that involves echoing attacker-supplied code into a user's browser instance. A browser instance can be a standard web browser client, or a browser object embedded in a software product such as the browser within WinAmp, an RSS reader, or an email client. The code itself is usually written in HTML/JavaScript, but may also extend to VBScript, ActiveX, Java, Flash, or any other browser-supported technology.</p>
<p align="justify">When an attacker gets a user's browser to execute his/her code, the code will run within the security context (or zone) of the hosting web site. With this level of privilege, the code has the ability to read, modify and transmit any sensitive data accessible by the browser. A Cross-site Scripted user could have his/her account hijacked (cookie theft), their browser redirected to another location, or possibly shown fraudulent content delivered by the web site they are visiting. Cross-site Scripting attacks essentially compromise the trust relationship between a user and the web site. Applications utilizing browser object instances which load content from the file system may execute code under the local machine zone allowing for system compromise.</p>
<p align="justify"></p>
<p align="justify">There are three types of Cross-site Scripting attacks: non-persistent, persistent and DOM-based.</p>
<p align="justify">Non-persistent attacks and DOM-based attacks require a user to either visit a specially crafted link laced with malicious code, or visit a malicious web page containing a web form, which when posted to the vulnerable site, will mount the attack. Using a malicious form will oftentimes take place when the vulnerable resource only accepts HTTP POST requests. In such a case, the form can be submitted automatically, without the victim's knowledge (e.g. by using JavaScript). Upon clicking on the malicious link or submitting the malicious form, the XSS payload will get echoed back and will get interpreted by the user's browser and execute. Another technique to send almost arbitrary requests (GET and POST) is by using an embedded client, such as Adobe Flash.</p>
<p align="justify">Persistent attacks occur when the malicious code is submitted to a web site where it's stored for a period of time. Examples of an attacker's favorite targets often include message board posts, web mail messages, and web chat software. The unsuspecting user is not required to interact with any additional site/link (e.g. an attacker site or a malicious link sent via email), just simply view the web page containing the code.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?p=1&amp;<wbr></wbr>cpage=javascript%3Aalert%281%29%3B</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">cpage</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">javascript:alert(1);</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Phase: Architecture and Design</p>
<p align="justify">Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid.</p>
<p align="justify">Examples of libraries and frameworks that make it easier to generate properly encoded output include Microsoft's Anti-XSS library, the OWASP ESAPI Encoding module, and Apache Wicket.</p>
<p align="justify"></p>
<p align="justify">Phases: Implementation; Architecture and Design</p>
<p align="justify">Understand the context in which your data will be used and the encoding that will be expected. This is especially important when transmitting data between different components, or when generating outputs that can contain multiple encodings at the same time, such as web pages or multi-part mail messages. Study all expected communication protocols and data representations to determine the required encoding strategies.</p>
<p align="justify">For any data that will be output to another web page, especially any data that was received from external inputs, use the appropriate encoding on all non-alphanumeric characters.</p>
<p align="justify">Consult the XSS Prevention Cheat Sheet for more details on the types of encoding and escaping that are needed.</p>
<p align="justify"></p>
<p align="justify">Phase: Architecture and Design</p>
<p align="justify">For any security checks that are performed on the client side, ensure that these checks are duplicated on the server side, in order to avoid CWE-602. Attackers can bypass the client-side checks by modifying values after the checks have been performed, or by changing the client to remove the client-side checks entirely. Then, these modified values would be submitted to the server.</p>
<p align="justify"></p>
<p align="justify">If available, use structured mechanisms that automatically enforce the separation between data and code. These mechanisms may be able to provide the relevant quoting, encoding, and validation automatically, instead of relying on the developer to provide this capability at every point where output is generated.</p>
<p align="justify"></p>
<p align="justify">Phase: Implementation</p>
<p align="justify">For every web page that is generated, use and specify a character encoding such as ISO-8859-1 or UTF-8. When an encoding is not specified, the web browser may choose a different encoding by guessing which encoding is actually being used by the web page. This can cause the web browser to treat certain sequences as special, opening up the client to subtle XSS attacks. See CWE-116 for more mitigations related to encoding/escaping.</p>
<p align="justify"></p>
<p align="justify">To help mitigate XSS attacks against the user's session cookie, set the session cookie to be HttpOnly. In browsers that support the HttpOnly feature (such as more recent versions of Internet Explorer and Firefox), this attribute can prevent the user's session cookie from being accessible to malicious client-side scripts that use document.cookie. This is not a complete solution, since HttpOnly is not supported by all browsers. More importantly, XMLHTTPRequest and other powerful browser technologies provide read access to HTTP headers, including the Set-Cookie header in which the HttpOnly flag is set.</p>
<p align="justify"></p>
<p align="justify">Assume all input is malicious. Use an "accept known good" input validation strategy, i.e., use a whitelist of acceptable inputs that strictly conform to specifications. Reject any input that does not strictly conform to specifications, or transform it into something that does. Do not rely exclusively on looking for malicious or malformed inputs (i.e., do not rely on a blacklist). However, blacklists can be useful for detecting potential attacks or determining which inputs are so malformed that they should be rejected outright.</p>
<p align="justify"></p>
<p align="justify">When performing input validation, consider all potentially relevant properties, including length, type of input, the full range of acceptable values, missing or extra inputs, syntax, consistency across related fields, and conformance to business rules. As an example of business rule logic, "boat" may be syntactically valid because it only contains alphanumeric characters, but it is not valid if you are expecting colors such as "red" or "blue."</p>
<p align="justify"></p>
<p align="justify">Ensure that you perform input validation at well-defined interfaces within the application. This will help protect the application even if a component is reused or moved elsewhere.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://projects.webappsec.org/Cross-Site-Scripting</p>
<p align="justify">http://cwe.mitre.org/data/definitions/79.html</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">79</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">8</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="red" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="high"></a>High (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">SQL Injection</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">SQL injection may be possible</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-trackback.php?p=1+AND+1%3D1+--+</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">p</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">1 AND 1=1 -- </font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The page results were successfully manipulated using the boolean conditions [1 AND 1=1 -- ] and [1 AND 1=2 -- ]
The parameter value being modified was NOT stripped from the HTML output for the purposes of the comparison
Data was returned for the original parameter.
The vulnerability was detected by successfully restricting the data originally returned, by manipulating the parameter</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Do not trust client side input, even if there is client side validation in place.  </p>
<p align="justify">In general, type check all data on the server side.</p>
<p align="justify">If the application uses JDBC, use PreparedStatement or CallableStatement, with parameters passed by '?'</p>
<p align="justify">If the application uses ASP, use ADO Command Objects with strong type checking and parameterized queries.</p>
<p align="justify">If database Stored Procedures can be used, use them.</p>
<p align="justify">Do *not* concatenate strings into queries in the stored procedure, or use 'exec', 'exec immediate', or equivalent functionality!</p>
<p align="justify">Do not create dynamic SQL queries using simple string concatenation.</p>
<p align="justify">Escape all data received from the client.</p>
<p align="justify">Apply a 'whitelist' of allowed characters, or a 'blacklist' of disallowed characters in user input.</p>
<p align="justify">Apply the privilege of least privilege by using the least privileged database user possible.</p>
<p align="justify">In particular, avoid using the 'sa' or 'db-owner' database users. This does not eliminate SQL injection, but minimizes its impact.</p>
<p align="justify">Grant the minimum database access that is necessary for the application.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/Top_10_2010-A1</p>
<p align="justify">https://www.owasp.org/index.php/SQL_Injection_Prevention_Cheat_Sheet</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">89</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">19</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="red" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="high"></a>High (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">SQL Injection</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">SQL injection may be possible</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-trackback.php?p=1+AND+1%3D1</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">p</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">1 AND 1=1</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The page results were successfully manipulated using the boolean conditions [1 AND 1=1] and [1 AND 1=2]
The parameter value being modified was NOT stripped from the HTML output for the purposes of the comparison
Data was returned for the original parameter.
The vulnerability was detected by successfully restricting the data originally returned, by manipulating the parameter</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Do not trust client side input, even if there is client side validation in place.  </p>
<p align="justify">In general, type check all data on the server side.</p>
<p align="justify">If the application uses JDBC, use PreparedStatement or CallableStatement, with parameters passed by '?'</p>
<p align="justify">If the application uses ASP, use ADO Command Objects with strong type checking and parameterized queries.</p>
<p align="justify">If database Stored Procedures can be used, use them.</p>
<p align="justify">Do *not* concatenate strings into queries in the stored procedure, or use 'exec', 'exec immediate', or equivalent functionality!</p>
<p align="justify">Do not create dynamic SQL queries using simple string concatenation.</p>
<p align="justify">Escape all data received from the client.</p>
<p align="justify">Apply a 'whitelist' of allowed characters, or a 'blacklist' of disallowed characters in user input.</p>
<p align="justify">Apply the privilege of least privilege by using the least privileged database user possible.</p>
<p align="justify">In particular, avoid using the 'sa' or 'db-owner' database users. This does not eliminate SQL injection, but minimizes its impact.</p>
<p align="justify">Grant the minimum database access that is necessary for the application.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/Top_10_2010-A1</p>
<p align="justify">https://www.owasp.org/index.php/SQL_Injection_Prevention_Cheat_Sheet</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">89</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">19</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="orange" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="medium"></a>Medium (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Application Error disclosure</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">This page contains an error/warning message that may disclose sensitive information like the location of the file that produced the unhandled exception. This information can be used to launch further attacks against the web application.The alert could be a false positive if the error message is found inside a documentation page.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-comments-post.php</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">N/A</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">HTTP 500 Internal server error</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Review the source code of this page</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">200</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="orange" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="medium"></a>Medium (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Directory browsing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">It is possible to view the directory listing.  Directory listing may reveal hidden scripts, include files , backup source files etc which be accessed to read sensitive information.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi:80/icons/</font></td>
</tr>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">Parent Directory</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Disable directory browsing.  If this is required, make sure the listed files does not induce risks.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">For IIS, turn off directory browsing.</p>
<p align="justify">For Apache, use the 'Options -Indexes' directive to disable indexes in directory or via .htaccess:</p>
<p align="justify">. http://httpd.apache.org/docs/mod/core.html#options</p>
<p align="justify">. http://alamo.satlug.org/pipermail/satlug/2002-February/000053.html</p>
<p align="justify">. or create a default index.html for each directory.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">548</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">48</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="orange" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="medium"></a>Medium (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Directory browsing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">It is possible to view the directory listing.  Directory listing may reveal hidden scripts, include files , backup source files etc which be accessed to read sensitive information.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/icons/</font></td>
</tr>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">Parent Directory</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Disable directory browsing.  If this is required, make sure the listed files does not induce risks.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">For IIS, turn off directory browsing.</p>
<p align="justify">For Apache, use the 'Options -Indexes' directive to disable indexes in directory or via .htaccess:</p>
<p align="justify">. http://httpd.apache.org/docs/mod/core.html#options</p>
<p align="justify">. http://alamo.satlug.org/pipermail/satlug/2002-February/000053.html</p>
<p align="justify">. or create a default index.html for each directory.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">548</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">48</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="orange" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="medium"></a>Medium (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Directory browsing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">It is possible to view the directory listing.  Directory listing may reveal hidden scripts, include files , backup source files etc which be accessed to read sensitive information.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi:80/icons/small/</font></td>
</tr>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">Parent Directory</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Disable directory browsing.  If this is required, make sure the listed files does not induce risks.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">For IIS, turn off directory browsing.</p>
<p align="justify">For Apache, use the 'Options -Indexes' directive to disable indexes in directory or via .htaccess:</p>
<p align="justify">. http://httpd.apache.org/docs/mod/core.html#options</p>
<p align="justify">. http://alamo.satlug.org/pipermail/satlug/2002-February/000053.html</p>
<p align="justify">. or create a default index.html for each directory.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">548</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">48</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="orange" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="medium"></a>Medium (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">Application Error disclosure</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">This page contains an error/warning message that may disclose sensitive information like the location of the file that produced the unhandled exception. This information can be used to launch further attacks against the web application.The alert could be a false positive if the error message is found inside a documentation page.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/admin-footer.php</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">N/A</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">HTTP 500 Internal server error</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Review the source code of this page</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">200</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?page_id=3</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?page_id=3</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?m=201405</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?m=201405</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Cookie set without HttpOnly flag</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">wordpress_test_cookie=WP+Cookie+check; path=/</font></td>
</tr>
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the HttpOnly flag is set for all cookies.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">www.owasp.org/index.php/HttpOnly</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Password Autocomplete in browser</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">AUTOCOMPLETE attribute is not disabled in HTML FORM/INPUT element containing password type input.  Passwords may be stored in browsers and retrieved.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">input</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">&lt;input type="password" name="pwd" id="user_pass" class="input" value="" size="20" tabindex="20" /&gt;</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Turn off AUTOCOMPLETE attribute in form or individual input elements containing password by using AUTOCOMPLETE='OFF'</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://msdn.microsoft.com/library/default.asp?url=/workshop/author/forms/autocomplete_ovr.asp</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">525</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-content/themes/default/style.css</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-content/themes/default/style.css</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=comments-rss2</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=comments-rss2</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>page_id=5</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>page_id=5</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/xmlrpc.php</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/xmlrpc.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-includes/wlwmanifest.xml</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-includes/wlwmanifest.xml</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/xmlrpc.php?rsd</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/xmlrpc.php?rsd</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?s=ZAP</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?s=ZAP</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-includes/js/comment-reply.js?ver=20090102</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-includes/js/comment-reply.js?ver=20090102</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>page_id=3</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>page_id=3</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Cookie set without HttpOnly flag</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?action=lostpassword</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">wordpress_test_cookie=WP+Cookie+check; path=/</font></td>
</tr>
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the HttpOnly flag is set for all cookies.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">www.owasp.org/index.php/HttpOnly</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?action=lostpassword</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?action=lostpassword</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?p=1</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?p=1</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/login.css?ver=20090514</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/login.css?ver=20090514</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/colors-fresh.css?ver=20090625</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/colors-fresh.css?ver=20090625</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>s=ZAP</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>s=ZAP</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>p=1</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>p=1</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?cpage=1&amp;<wbr></wbr>p=1</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?cpage=1&amp;<wbr></wbr>p=1</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-comments-post.php</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-comments-post.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/install.css</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/install.css</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Cookie set without HttpOnly flag</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">wordpress_test_cookie</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">WP+Cookie+check; path=/</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the HttpOnly flag is set for all cookies.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">www.owasp.org/index.php/HttpOnly</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Cookie set without HttpOnly flag</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?action=lostpassword</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">wordpress_test_cookie</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">WP+Cookie+check; path=/</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the HttpOnly flag is set for all cookies.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">www.owasp.org/index.php/HttpOnly</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Cookie set without HttpOnly flag</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?redirect_to=http%3A%2F%2Fwww.kipito.fi%2Fwp-admin%2F</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">wordpress_test_cookie=WP+Cookie+check; path=/</font></td>
</tr>
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the HttpOnly flag is set for all cookies.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">www.owasp.org/index.php/HttpOnly</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?redirect_to=http%3A%2F%2Fwww.kipito.fi%2Fwp-admin%2F</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Password Autocomplete in browser</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">AUTOCOMPLETE attribute is not disabled in HTML FORM/INPUT element containing password type input.  Passwords may be stored in browsers and retrieved.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?redirect_to=http%3A%2F%2Fwww.kipito.fi%2Fwp-admin%2F</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">input</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">&lt;input type="password" name="pwd" id="user_pass" class="input" value="" size="20" tabindex="20" /&gt;</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Turn off AUTOCOMPLETE attribute in form or individual input elements containing password by using AUTOCOMPLETE='OFF'</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://msdn.microsoft.com/library/default.asp?url=/workshop/author/forms/autocomplete_ovr.asp</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">525</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?redirect_to=http%3A%2F%2Fwww.kipito.fi%2Fwp-admin%2F</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Cookie set without HttpOnly flag</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?redirect_to=http%3A%2F%2Fwww.kipito.fi%2Fwp-admin%2F</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Parameter</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">wordpress_test_cookie</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Attack</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">WP+Cookie+check; path=/</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the HttpOnly flag is set for all cookies.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">www.owasp.org/index.php/HttpOnly</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">13</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Web Browser XSS Protection Not Enabled</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Web Browser XSS Protection is not enabled, or is disabled by the configuration of the 'X-XSS-Protection' HTTP response header on the web server</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/admin-footer.php</font></td>
</tr>
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">Other information</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">The X-XSS-Protection HTTP response header allows the web server to enable or disable the web browser's XSS protection mechanism. The following values would attempt to enable it: 
X-XSS-Protection: 1; mode=block
X-XSS-Protection: 1; report=http://www.example.com/xss
The following values would disable it:
X-XSS-Protection: 0
The X-XSS-Protection HTTP response header is currently supported on Internet Explorer, Chrome and Safari (WebKit).
Note that this alert is only raised if the response body could potentially contain an XSS payload (with a text-based content type, with a non-zero length).</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the web browser's XSS filter is enabled, by setting the X-XSS-Protection HTTP response header to '1'.</p>
</font></td>
</tr>
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet</p>
<p align="justify">https://blog.veracode.com/2014/03/guidelines-for-setting-security-headers/</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>CWE Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">933</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>WASC Id</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">14</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="yellow" height="24">
<a name="low"></a><td width="20%" valign="top"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">Low (Warning)</font></strong></td><td width="80%"><strong><font color="#000000" size="2" face="Arial, Helvetica, sans-serif">X-Content-Type-Options header missing</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'.</p>
<p align="justify">This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.</p>
<p align="justify">Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/admin-footer.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p>
<p align="justify">If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify"></p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?page_id=3</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?m=201405</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-content/themes/default/style.css</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=comments-rss2</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>page_id=5</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/xmlrpc.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-includes/wlwmanifest.xml</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/xmlrpc.php?rsd</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?s=ZAP</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-includes/js/comment-reply.js?ver=20090102</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>page_id=3</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?action=lostpassword</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?p=1</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/login.css?ver=20090514</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/colors-fresh.css?ver=20090625</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>s=ZAP</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?feed=rss2&amp;<wbr></wbr>p=1</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/?cpage=1&amp;<wbr></wbr>p=1</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-comments-post.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/css/install.css</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-login.php?redirect_to=http%3A%2F%2Fwww.kipito.fi%2Fwp-admin%2F</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
<p></p>
<table width="100%" border="0">
  
  
<tr bgcolor="blue" height="24">
<td width="20%" valign="top"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif"><a name="info"></a>Informational (Warning)</font></strong></td><td width="80%"><strong><font color="#FFFFFF" size="2" face="Arial, Helvetica, sans-serif">X-Frame-Options header not set</font></strong></td>
</tr>
  
  
  
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Description</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks</p>
</font></td>
</tr>
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%">
<blockquote>
<font size="2" face="Arial, Helvetica, sans-serif">URL</font>
</blockquote>
</td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">http://www.kipito.fi/wp-admin/admin-footer.php</font></td>
</tr>
  
  
  
<TR vAlign="top">
<TD colspan="2"></TD>
</TR>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Solution</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY.  ALLOW-FROM allows specific websites to frame the web page in supported web browsers).</p>
</font></td>
</tr>
  
<tr bgcolor="#e8e8e8" valign="top">
<td width="20%"><font size="2" face="Arial, Helvetica, sans-serif">
<p>Reference</p>
</font></td><td width="80%"><font size="2" face="Arial, Helvetica, sans-serif">
<p align="justify">http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx?Redirected=true</p>
</font></td>
</tr>

</table>
</body>
</html>
