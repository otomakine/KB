<a id="home">Home:</a>
<br>
[TCP](#TCP "TCP/IP model")
[OSI](#OSI "OSI model")
[HTTP](#HTTP "Hypertext Transfer Protocol, TCP :80, TCP/IP model: App lyr, OSI: highest 7th lyr")
[HTTPS](#HTTPS "Hypertext Transfer Protocol Secure, TCP :443, TCP/IP model: App lyr, OSI: highest 7th lyr") 
<br>
[CI](#CI "Continuous intergration (code is commited & tested)")
[CD](#CD "Continuouse delivery (CI + deployed in prod)"):
[Jenkins](#Jenkins "Jenkins")
[GHA](#GHA "GitHub Actions")
[TFS](#TFS "MS Team Fonation Server, up to 2018")
[ADevOps](#ADevOps "MS Azure DevOps, ")
[TC](#TeamCity "Team City")
<br>
[Git](#Git "Git, bought by MS")
[TFVC](#TFVC "Team Fondation Version Control")
<br>
[Data](#Data "Data"):
<br>
[SQL](#SQL "SQL"):
<br>
[NoSQL](#NoSQL "NoSQL"):
<br>
[EXT](#EXT "Extensions"):
[MD](#MD "Markdown")
<br>
[PY](#PY "some test<br>some text<br>some text<br>'''<br>test<br>'''<br>some text<br>some text"):
[Inst](#PYInst "Python installation & configuration")
[[]](#[] "Lists")
[{}](#{} "Dictionaries")
[()](#() "Tuples")
[VAR](#VAR "Variabes")
<br>
[PT](#PT "Pytest"):
[Inst](#PTInst "Pytest installation & configuration")
[Mods](#PTmods "Pytest specific modules")
[Asserts](#PTAsserts "Asserts")
<br>
[PW](#PW "Playwright"):
[Inst](#PWInst "Playwright installation & configuration")


# Contents:
### <a id="MD">MD</a>
[home](#home)
test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1test1
- Line above is 145 chars, it is OK for m1 laptops (what if other chars are used?)
- My ext mon can support even 149 chars
- Inspired by https://gist.github.com/Jekins/2bf2d0638163f1294637#some-title-1
- Folding text <details><summary>Каков вопрос</summary>Таков и ответ</details> 

### <a id="HTTP">HTTP</a>
[home](#home)
- Hypertext Transfer Protocol, TCP :80, 

### <a id="HTTPS">HTTPS</a>
[home](#home)
- Hypertext Transfer Protocol, TCP :443
- SSL/TLS are encr transport mechs: [Secure Sockets Layer & Transport Layer Security] 
- SSL/TLS: (1995 Netscape) SSL = TLS 1.0 > (>2005 IETF) TLS 1.1/TLS1.2
- Server sends cert to client, client verifies & connection is opened (protocol RFC2459)
- If info in cert does not corresponds to server URI user is warned
- Client also send its info to server (same protocol RFC2459)
- Certs by cert centers which verify owners of sites
- Self-signed: certs can be prepared by IT team and w/o cert center
- HSTS forces HTTP to use HTTPS for sites which use both
- Hacker can substitute original cert with open key sent by server with his own if he is between client & server, expecially if certs are self-signed & both cli & srv will think that communication is secure

### <a id="ADevOps">Azure DevOps</a>
[home](#home)
- Wiki: https://en.wikipedia.org/wiki/Azure_DevOps_Server

### <a id="Jenkins">Jenkins</a>
[home](#home)
- 1HR: https://youtu.be/yTNQnSKqKis?t=1006
- Merion Academy short: https://www.youtube.com/watch?v=CtHcrmRplJI

### <a id="PY">PY</a>
[home](#home)
- PY RU 1hr: https://www.youtube.com/watch?v=aySjqUWbU3E

### <a id="{}">{}</a>
[home](#home)
- Dictionary

### <a id="PT">Pytest</a>
[home](#home)
- Ls4 https://www.youtube.com/watch?v=6QjDW-p_F-o&list=PLB2iiSfKWtvykq9s0plSVI_Du60i0iphU&index=4

### <a id="PT">Playwright</a>
[home](#home)
- Into https://habr.com/ru/articles/597293/
