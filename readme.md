<a id="home">Heap of Contents:</a>
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
[Git](#Git "Git, bought by MS, clone, commit -am <msg>, ")
[TFVC](#TFVC "Team Fondation Version Control")
[Term](#Terminal "Terminal commands")
<br>
[Data](#Data "Data"):
<br>
[SQL](#SQL "SQL"):
[PostgreSQL](#PostgreSQL "PostgreSQL")
[MSSQL](#MSSQL "MSSQL")
[MySQL](#MySQL "MySQL")
[SQLite](#SQLite "SQLite")
<br>
[NoSQL](#NoSQL "NoSQL"):
[Mongod](#Mongod "Mongod")
[Redis](#Redis "Redis")
[Cassandra](#Cassandra "Cassandra")
<br>
[EXT](#EXT "Extensions"):
[MD](#MD "Markdown")
<br>
[PY](#PY "some test<br>some text<br>some text<br>'''<br>test<br>'''<br>some text<br>some text"):
[Inst](#PYInst "Python installation & configuration")
[PyCharm](#PyCharm "PyCharm")
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
[PowerShell](#PowerShell "PowerShell"):
[Variables](#PSVars "PowerShell Variables")
[Cycles](#PSCycles "PowerShell Cycles")
<br>
[PW](#PW "Playwright"):
[Inst](#PWInst "Playwright installation & configuration")
<br>
[QA](#QA "QA"):
<br>
[TDT](#TDT "Test Design Techniques"):
<br>
[AUT](#AUT "Automation"):
[Se](#Selenium "Selenium, jasmine-trx-reporter, jasmine-spec-reporter"): 
<br>
[Int](#Int "Interview"):
[Ach](#Ach "Achievements")
[Fail](#Fail "Fails")
<br>

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

### <a id="Git">Git</a>
[home](#home)
- cheatsheet https://training.github.com/downloads/ru/github-git-cheat-sheet/
- (usr setup) ```git config --global user.name "name", config --global user.email "e-mail"```
- (creation) ```git init``` (new prj) , ```clone -b $GitBranch --progress (error stream to terminal) --verbose (details)```
- (edittig) ``` git status``` (overall), ```add .```, ```diff --staged``` (diff last), ```reset "file"``` (removes indexing), ```commit -ma "msg"```
- (file ops) ``` git pull -v``` (verbose)
- (undo) ```git reset --hard``` (resets)
- (other) ```git difftool``` (run outer tool), ```rm``` (remove), ```mv``` (move), ```clean``` (rubbish)
- (patching) ```git merge``` (merge branches),
- (ignoring) ```*.log, build/, temp-*```
- (list ignored) ```git ls-files --others --ignored --exclude-standard```
```powershell
$GitBranch = Select-XML -path $TestConfig -xpath "/config/GitBranch"
$GitBranch = $GitBranch -replace ':.*', ''
$GitFolderName = "eiv-apps-aut"
[string]$GitDir = "C:\_projects"
[string]$LogDir = "$GitDir\eiv-apps-aut\src\results"
[string]$PullGitOperation = "pull -v" #default GIT operation if GIT CLONE has been already executed today
[string]$GitReset = "reset --hard HEAD"
[string]$CloneGitOperation = "clone https://PAT:<pat><site>/<dir>/_git/eiv-apps-aut -b $GitBranch --progress --verbose"
[string]$GitFlagName = ""
[string]$GitFlagsLoc = "$WorkDir\gitflags"
Set-Location "$GitDir\eiv-apps-aut"
$GitFlagName = Get-Date -Format "ddMMyy"
```
### <a id="Terminal">Terminal</a>
[home](#home)
- (base) ```ls, cd, mkdir, rmdir``` (files) ```touch, rm, cat (contents), echo, man (help)```
- (system) ```update (worktime), top (act procs), ps (all procs), kill, reboot, useradd, userdel, passwd (ch pswd), sudo```
- (users) ```id, last (entry history), who (auth list), groupadd “testgroup”, adduser/deluser,usermod NewUser```
- (network) ```ip, ping, ifconfig, route (trace?), ssh, scp (copy data via ssh), wget (web get files)```
- (packages) ```apt (Deb\Ubuntu), yum (Red Hat CentOS), pacman (Ach Linux)```
- (browse) ```cd /. (up), cd, cd/root, cd .. (down), cd /root/.ssh```
- (dirs) ```mkrdir NewDir, rm -rf NewDir (r+f), cp -r olddir1 newdir2```
- (files1) ```ls -al. pwd (show curr dir), rm NewFile, cp oldfile1 newfile2 (cpy contents), mv oldfile1 newfile2 (ren), wc ShwFileStats```
- (files2) ```touch newEmptyFile, more ShwContIncrement, head Shw1st10Lines, tail ShwLast10Lines, gpg -c newfile (encr wpass), gpg newfile.gpg (decr)```
- (text) ```vi, nano, grep, sed (edit), awk (txt data edit)```
- (images) ```feh (view), gimp (editor), convert (conv)```
- (video) ```vlp (plr), ffmpeg (editor), mencoder (conv)```
- (audio) ```mpv (plr), audacity (editor), sox (conv)```
- (db) ```mysql, postgresql, sqlite3```
- (wsrv) ```apache2, nginx, uwsgi (uWSGI)```

### <a id="PowerShell">PowerShell</a>
[home](#home)
```powershell
Clear/Write-Host, Test-Path, New-Folder/Item/
ConvertFrom/To-Csv/Json/Markdown/Html
Get/Start/Stop-Service/Job
Get-Date/Host/
Get-Process | Select-Object -Property [] | Sort-Object -Property [] | Out-File -FilePath <str>
Join-String
Measure-Command
New-Object/File
Out-File/GridView
Read/Write-Host
```
### <a id="PSVars">PowerShell Variables</a>
[home](#home)
```powershell
$MyVariable = 1, 2, 3
$Path = "C:\Windows\System32"
$Processes = Get-Process
$Today = (Get-Date).DateTime
```

### <a id="PSCycles">PowerShell Cycles</a>
[home](#home)
```powershell
while($val -ne 3){$val++; Write-Host $val}

$i = 1
Write-Host "Waiting for TRX file ..."
do {
    if (Test-Path $TRXpath) { Write-Host "TRX file found"; Break }
    else { Write-Host "TRX file not found: $i" }
    Start-Sleep -Seconds (1)
    $i++
} while ($i -le 1 * 3)
```

### <a id="PY">PY</a>
[home](#home)
- PY RU 1hr: https://www.youtube.com/watch?v=aySjqUWbU3E

### <a id="{}">{}</a>
[home](#home)
- Dictionary

### <a id="PT">Pytest</a>
[home](#home)
- Ls4 https://www.youtube.com/watch?v=6QjDW-p_F-o&list=PLB2iiSfKWtvykq9s0plSVI_Du60i0iphU&index=4

### <a id="PW">Playwright</a>
[home](#home)
- Docs https://playwright.dev/docs/intro
- Into https://habr.com/ru/articles/597293/

### <a id="QA">QA</a>
[home](#home)

### <a id="TDT">TDT</a>
[home](#home)

### <a id="Int">Interview</a>
[home](#home)

### <a id="Ach">Achievements</a>
[home](#home)
me/me
- ROR dev: Re-run ASAP > QA Aut want > higher priority added
- ROR dev: Re-run ASAP & create bak > Devs want > even higher priority & backs added
- PS dev: Logs & baks clean-up > Massive tests filled shares > CI/CD task added (daily-nightly)
- ROR dev: results > QAs want to send info to devs > Envelop icon opens Outlook ()
- Portal results less clicks > QAs want to analyze results faster > P draws icons using result stats
- Execute Web S 1by1 > QAs told W results are too big >
- 1ms timeouts
- Cl VMs On/Off

### <a id="Fail">Failures</a>
[home](#home)
- Portal halted & AZ Queue sent/lost all results > Parsed logs in cold blob & re-sent results to Portal (logs had JSONs)

