# Application Security Engineer Interview Questions
Here are some common interview questions for an application security position you can review for your own interview, along with example answers

# non technical questions

**1. Why do you want to work in application security?**
  * Example: "I've loved working with computers ever since I was little and built one with my dad. Computers have a set of rules that need to be followed in order for them to work properly. I love being able to find the right solution in code that helps protect programs from those who try to make them less secure."

**2. How do you deal with stressful situations?**
  * Example: "I approach stressful situations with a deep breath and a different perspective. About a month ago at my previous position, I was having trouble with a set of code. I read through it many times but was never able to find the problem, and the situation became very stressful. I took a minute to relax and asked a coworker for some help. After looking over the code together, we were able to find the fix."


__3. What are your greatest strengths in app security?__
  * Example: "Over the last few years, I have gotten very strong at detecting intrusions and finding the weak points of security code. I developed my skills through habitual practice. First, I run the code through an intrusion detection program, then I conduct some manual tests myself. It's important to catch errors in the program's security and errors in the intrusion detection program."

__4. What are your greatest weaknesses in app security?__
  * Example: "I often write my code very quickly, which can sometimes result in small mistakes that take time to correct. I know that this weakness is fixable through practice, however, so when I write code I've recently begun to remind myself to slow down and take my time. This practice has already helped me improve my accuracy greatly, and I will continue to work on improving it."

__5. Why do you want to work for this company?__
  * Example: "I've been following this company's work and progress for a little while now, and I love what you're achieving in the world of application security. From your work and coding on password protection software to your work with individual clients, you've shown yourselves to be an essential part of the app security world. I would love to be a part of this team and your company's continued development."

__6. What's a time you disagreed with a decision a programming lead made?__
  * Example: "A few months ago, my programming lead tried to rush our team to turn in some of our codes without completing all the necessary intrusion detection checks. This rush could have resulted in a few errors or codes that didn't work properly, but I also understood that deadlines needed to be met. I brought this issue up to my lead to see if there were ways to work around it. Eventually, my team compromised with the lead and we all stayed for an extra hour every day that week to finish the intrusion checks and meet the deadline."

__7. What's your application security experience?__
  * Example: "When I was in college, I started a club with the assistance of a professor to help students understand the basics of application security. The club allowed students to practice writing code protecting programs and infiltrating them. After graduation I took at a job at Foltess Security as an application security programmer. There, I helped to optimize our coding output, and the company promoted me to lead programmer shortly after."

__8. What do you like best about your current role?__
  * Example: "My programming team has been the best part of my current role. Every day they come to work with a positive attitude. This helps us collaborate better together and creates an atmosphere that welcomes questions and support. I am excited to join a similar team here at Web Security."

__9. Why are you leaving your current role?__
  * Example: "Though my time at Foltess Security has been wonderful, I am looking for new opportunities to continue to learn and grow in application security. I believe that this company can give me that opportunity and strengthen my skills as a computer programmer."

__10. Do you have any questions for me?__
  * Example: "Yes! I would love to know more about Web Security's team of coders and what their daily assignments are like."



# technical questions

* Which architecture is more secure? 2 tier or 3 tier
* Explain SSL Handshake
  * https://www.youtube.com/watch?v=ubHZQrECeew
  * https://www.cloudflare.com/learning/ssl/how-does-ssl-work/
  * https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/
* Recommend XXE mitigation for application which requires external entities to be called because of business requirement
  * Patch or upgrade all XML processors and libraries in use by the application or on the underlying operating system. Use dependency checkers. Update SOAP to SOAP 1.2 or higher.
  * Disable XML external entity and DTD processing in all XML parsers in the application, as per the OWASP Cheat Sheet 'XXE Prevention'.
  * Implement positive ("whitelisting") server-side input validation, filtering, or sanitization to prevent hostile data within XML documents, headers, or nodes. 
* Explain CORS and SOP
  * https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS
  * https://portswigger.net/web-security/cors
  * https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy
  * https://www.bedefended.com/papers/cors-security-guide
* Does SOP mitigate CSRF attacks?
  * https://security.stackexchange.com/questions/157061/how-does-csrf-correlate-with-same-origin-policy
  * In short SOP only prevents reading data which was served from a different origin. It does not cover cross-domain form submissions which are used to carry out a CSRF attack.
* Exploiting SSRF attacks
  * https://portswigger.net/web-security/ssrf
  * https://www.hackerone.com/blog-How-To-Server-Side-Request-Forgery-SSRF
  * https://blog.appsecco.com/an-ssrf-privileged-aws-keys-and-the-capital-one-breach-4c3c2cded3af
* What is web cache deception?
  * https://blog.cloudflare.com/understanding-our-cache-and-the-web-cache-deception-attack/
  * http://omergil.blogspot.com/2017/02/web-cache-deception-attack.html
  * https://portswigger.net/research/practical-web-cache-poisoning
  * Please note that web caches also enable a different type of attack called Web Cache Deception which should not be confused with cache poisoning.
* What is HTTP request smuggling?
  * http://projects.webappsec.org/w/page/13246928/HTTP%20Request%20Smuggling
  * https://portswigger.net/web-security/request-smuggling
  * Burp Suite automatically unpacks chunked encoding to make messages easier to view and edit.
  * Browsers do not normally use chunked encoding in requests, and it is normally seen only in server responses.
* Explain DOM XSS. Can DOM XSS be stored? Can CSP header mitigate dom based XSS
  * https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/
  * https://html.spec.whatwg.org/multipage/parsing.html
  * https://portswigger.net/web-security/cross-site-scripting/dom-based
  * https://brutelogic.com.br/blog/dom-based-xss-the-3-sinks/
  * https://www.scip.ch/en/?labs.20171214
  * Reflected and Stored XSS are server side injection issues while DOM based XSS is a client (browser) side injection issue.
  * DOM XSS combined with reflected and stored data
  * CSP does not stop DOM-based XSS (also known as client-side XSS)
  * CSP can bypss with "script-src-elem" header, you can overwrite existing script-src rules in CSP and enabling you to inject unsafe-inline
* What will be your testcase for a file upload functionality?
  * https://medium.com/@satboy.fb/art-of-unrestricted-file-upload-exploitation-92ed28796d0
  * https://resources.infosecinstitute.com/file-upload-vulnerabilities/#gref
  * https://pentestlab.blog/2012/11/19/abusing-file-upload/
  * https://pentestlab.blog/2012/11/29/bypassing-file-upload-restrictions/
* What is HSTS?
  * https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security
* Explain SSL Stripping
  * https://blog.cloudflare.com/performing-preventing-ssl-stripping-a-plain-english-primer/
  * SSL stripping is a technique that downgrades your connection from secure HTTPS to insecure HTTP.
  * [sslstrip+](https://github.com/LeonardoNve/sslstrip2) avoid (HSTS) protection mechanism with dns proxy, only solution for preventation is DNSSEC.
* If you have API calls which need to fetch credentials, what will be the secure way to store secrets and making them available for API calls?
  * https://medium.com/hackernoon/where-do-you-keep-credentials-for-your-lambda-functions-cac746048480
  * Use a .env file — which is committed to the repo
  * Use a .secrets file ( basically the .env file above but encrypted via serverless secrets plugin
* How does file compression work?
* Which method is secure? Compress First and then Encrypt the data or Encrypt First then Compress
  * Compress and then encrypt is better. Data compression removes redundant character strings in a file. So the compressed file has a more uniform distribution of characters. This also provides shorter plaintext and ciphertext, which reduces the time spent encrypting, decrypting and transmiting the file.
* You have found a vulnerability a product/infrastructure, how will you investigate if this was not exploited already by an attacker
* What is SPF, DKIM and DMARC?
  * https://www.smartertools.com/blog/2019/04/09-understanding-spf-dkim-dmarc
  * https://www.endpoint.com/blog/2014/04/15/spf-dkim-and-dmarc-brief-explanation
  * https://www.reddit.com/r/sysadmin/comments/aph6ee/lets_talk_about_email_spoofing_and_prevention_alt/
* Explain DNS Exfiltration
* Explain Log Poisoning using LFI/RFI
* https://www.hackingarticles.in/apache-log-poisoning-through-lfi/
  * https://www.hackingarticles.in/rce-with-lfi-and-ssh-log-poisoning/
  * https://highon.coffee/blog/lfi-cheat-sheet/
* Do the HttpOnly cookie and X-XSS-Protection header mitigate cross-site scripting attacks?
* How do you exploit XSS in a post request?
  * https://portswigger.net/blog/exploiting-xss-in-post-requests
* Difference: IDOR, Missing function level access control and privilege escalation
* How does burp suite work with HTTPs requests?
  * https://www.quora.com/How-is-it-possible-that-a-proxy-tool-like-Burp-Suite-is-able-to-decrypt-HTTPS-communication-like-plain-text-credentials
  * https://portswigger.net/burp/documentation/desktop/tools/proxy/using
* Is the DNS service's communication encrypted?
* Security implications in DNS
* DNS over HTTPs
  * https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https/
  * https://www.chromium.org/developers/dns-over-https
* How does ssh authentication work?
  * https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process
  * https://gravitational.com/blog/ssh-handshake-explained/
  * client create public key and send them to the server
    * server create Key Exchange (secret key) and encrypt with client public key and send
    * client decrypt message and use this secret key for symetric encryption
* How to create and implement an SSL certificate?
* How to verify if a database is encrypted?
* If you want a script to use credentials from the system, where will you store the credentials?
* Explain SDLC
* In which phase of SDLC should security be integrated?
* Explain encryption in Wifi network communication.
* What are stateless and stateful requests?
  * https://www.geeksforgeeks.org/difference-between-stateless-and-stateful-protocol/
* How is the state of a request saved in HTTP?
* What data does the shadow file contains?
  * https://www.cyberciti.biz/faq/understanding-etcshadow-file/
* What is salt in cryptography?
* What is Double-Submit Cookie?
* What is Preflight request?
  * https://developer.mozilla.org/en-US/docs/Glossary/Preflight_request
* What are Certificate Transparency Logs?
* What is your favourite vulnerability and why?
* Talk about any latest/interesting vulnerability or breach you learnt about.
