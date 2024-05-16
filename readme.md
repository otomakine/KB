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
[CD](#Coding "Coding"):
[OOP](#OOP "OOP")
<br>
[PY](#PY "some test<br>some text<br>some text<br>'''<br>test<br>'''<br>some text<br>some text"):
[Inst](#PYInst "Python installation & configuration")
[PyCharm](#PyCharm "PyCharm")
[[]](#[] "Lists")
[{}](#{} "Dictionaries")
[()](#() "Tuples")
[VAR](#VAR "Variabes")
[Fun](#PyFun "some funny expressions & what they return")
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
[TDT](#TDT "Test Design Techniques: 1. Классы эквивалентности (диапазоны, 1) 2. Граничные значения (границы, 1-2-3) 3. Причинно-следственный анализ (карта причин и откликов) 4. Прогнозирование ошибок (негативные тесты) 5. Попарное тестирование (pair-wise, 3x3, 9 vs 27) 6. Диаграмма состояний (диаг сост типа флоу Jira) 7. Таблица принятия решений (decision table, Pos&N х T/F = Results)")
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

### <a id="Mongod">Mongod</a>
[home](#home)
- cluster.db.collection
- pass, cert(more safe)
- json document db, unique ids
- for non-structured data
- if notExists then will be created
- if no collections left, db is dropped
- ids can be custom & short, eg 1
```
db = cluster.db
coll = db.users
for v in coll.find(); print(v)
insertOne(json)
insertMany(json_data)

query = {"status": True}; for v in coll find(query, {"_id": 0, "status": 1}); print(v) # don’t show id ((!) “0” works for _id only, “1” is ok for other keys), show status
$gt, $regex
$regex # query{“name”: {“$regex”: “test*”}} or query{“name”: {“$regex”: “test.”}} # asterix or dot
find_one: find_one({“name”: “test3”}) # returns only one & 1st document
sort # for v in coll.find().sort{“name”, 1} # “1” for asc, “-1” for desc
limit # 
count_documents # res = coll.count_documents({}); print(res) 
list_collection_names # res = db.list_collection_names(); print(res)
drop # coll.drop()
insert_one # for i in range(20): coll.insert_one({“_id”: i, “name”: f”test{i}”})
update_one # current = {"name": "test3"}; new_data = {"$set": {"name": "new"}}; coll update_one(current, new_data)
update_many # current = {"name": {"$regex": "test."3}; new _data = {"$set": {"name": "new" 3}; coll update_many(current, new _data)
delete_one # coll.delete_one({"_id" : 0})
delete_many # query = {"name222" : {"$regex" : "new2"}}; coll.delete_many(query)
delete_many # all # res = coll.delete_many({}); print("deleted: ", res.deleted_count)
deleted_count # query = {"name": {"$regex" : "new*"}}; res = coll.delete_many(query); print("deleted: ", res.deleted_count)
create_index # coll.create_index([("name", pymongo.DESCENDING)]); print(coll.index_information())
$set # see above
$inc # increment # current={"_id": 1}; new_data={"$inc": {"balance": -100}}; coll.update_many(current, new_data)
$pop # remove, by val ind; 1 stands for 2nd # current = {"_id": 1}; new_data = {"$pop": {"arrage": 1}}; coll update_one(current new_data) 
$pull # remove, by val txt # current = {"_id" : 1}; new_data = {"$pull" : {"arrage": "hello"}}; coll update_one(current new_data)
```
### <a id="ADevOps">Azure DevOps</a>
[home](#home)
- Wiki: https://en.wikipedia.org/wiki/Azure_DevOps_Server

### <a id="Jenkins">Jenkins</a>
[home](#home)
- 1HR: https://youtu.be/yTNQnSKqKis?t=1006
- Merion Academy short: https://www.youtube.com/watch?v=CtHcrmRplJI
- Java based, 2 jar files (Master/Controller+Agents=Node) 
- <2008 Hundson (bought by Oracle), >2008 Jenkins (MIT)
- Agents: can be on Linix, Win, macOS
- Modules: jobs, users, plugins (eg pipeline), credentials (for integration), node/cloud (SlaveNodesAgent (SSH) / CloudSlaves (API) ), global configs (settings)
- Tasks: jobs
- Keys: via ssh-keygen primary & public (.pub)
- pipeline { agent (any) stages > steps
- when, always, success
- Languages: Groovy or Scripted Style
- Ubuntu installation:
```
Step 1: Install Java
$ sudo apt update
$ sudo apt install openjdk-8-jdk

Step 2: Add Jenkins Repository
$ wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add –

Step 3: Add Jenkins repo to the system
$ sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

Step 4: Install Jenkins
$ sudo apt update
$ sudo apt install Jenkins

Step 5: Verify installation
$ systemctl status Jenkins

Step 6: Once Jenkins is up and running, access it from the link:
http://localhost:8080
```

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

### <a id="Coding">Coding</a>
[home](#home)
- CS50 https://www.youtube.com/playlist?list=PLawfWYMUziZqyUL5QDLVbe3j5BKWj42E5

### <a id="SOLID">SOLID Principles</a>
[home](#home)
```
S - Single Responsibility (кажд кл своё)
O - Open closed (откр для расш, но з д измен)
L - BarLiskov substitution (
I - Interface Segregation (кл не должен реал интерф к которому нет отношения)
D - Dependency Inversion (верх не зависит от низов, детали зависят от абстракций)
```
на примерах https://habr.com/ru/articles/688530/ 
```
SOLID - это принципы разработки программного обеспечения, следуя которым Вы получите хороший код, который в дальнейшем будет хорошо масштабироваться и поддерживаться в рабочем состоянии.
S - Single Responsibility Principle - принцип единственной ответственности. Каждый класс должен иметь только одну зону ответственности.
O - Open closed Principle - принцип открытости-закрытости. Классы должны быть открыты для расширения, но закрыты для изменения.
L - Liskov substitution Principle - принцип подстановки Барбары Лисков. Должна быть возможность вместо базового (родительского) типа (класса) подставить любой его подтип (класс-наследник), при этом работа программы не должна измениться.
I -  Interface Segregation Principle - принцип разделения интерфейсов. Данный принцип обозначает, что не нужно заставлять клиента (класс) реализовывать интерфейс, который не имеет к нему отношения.
D - Dependency Inversion Principle - принцип инверсии зависимостей. Модули верхнего уровня не должны зависеть от модулей нижнего уровня. И те, и другие должны зависеть от абстракции. Абстракции не должны зависеть от деталей. Детали должны зависеть от абстракций.
```
### <a id="Patterns">Patterns</a>
[home](#home)
- Паттерн — устоявшийся способ решения типовой задачи
- В метафорах https://habr.com/ru/articles/136766/
- В автотестировании https://habr.com/ru/companies/jugru/articles/338836/ 

#### Архитектурные
```
- Active Record (каждая таблица базы данных превращается в класс, каждая строка таблицы в объект этого класса, RoR, CakePHP, Castle & etc)
```
#### Порождающие паттерны
Паттерны которые создают новые объекты, или позволяют получить доступ к уже существующим. То есть те шаблоны, по которым можно создать новый автомобиль и как это лучше сделать.
```
- Singleton (одиночка)
- Registry (реестр, журнал записей)
- Multiton (пул «одиночек»)
- Object pool (пул объектов)
- Factory (фабрика)
- Builder (строитель)
- Prototype (прототип)
- Factory method (фабричный метод)
- Lazy initialization (отложенная инициализация)
- Dependency injection (внедрение зависимости)
- Service Locator (локатор служб)
```
#### Структурирующие паттерны
Данные паттерны помогают внести порядок и научить разные объекты более правильно взаимодействовать друг с другом.
```
- Adapter или wrapper (адаптер, обертка)
- Bridge (мост)
- Composite (компоновщик)
- Decorator (декоратор, оформитель)
- Facade (фасад)
- Front controller (единая точка входа)
- Flyweight (приспособленец)
- Proxy или surrogate (прокси, заместитель, суррогат)
```
#### Паттерны поведения
Эта группа паттернов позволяет структурировать подходы к обработке поведения и взаимодействия объектов. Проще говоря, как должны проходить процессы в которых существует несколько вариантов протекания событий.
```
- Chain of responsibility (цепочка обязанностей)
- Command или action (команда, действие)
- Interpreter (интерпретатор)
- Iterator (итератор, указатель)
- Mediator (посредник)
- Memento (хранитель)
- Observer или Listener (наблюдатель, слушатель)
- Blackboard (доска объявлений)
- Servant (слуга)
- State (состояние)
- Strategy (стратегия)
- Specification (спецификация, определение)
- Subsumption (категоризация)
- Visitor (посетитель)
- Single-serving visitor (одноразовый посетитель)
- Hierarchical visitor (иерархический посетитель)
```
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

### <a id="PY">Python</a>
[home](#home)
- PY RU 1hr: https://www.youtube.com/watch?v=aySjqUWbU3E
- Интепретируемый
- pip/pip3 package manager
- integers, float, “strings”, [lists], (tuples), {sets}, {dictionaries}

### <a id="PyFun">Python Fun</a>
[home](#home)
```python
extend() # l = [1, 2, 3]; l.extend('abc'); print(l) # [1, 2, 3, 'a', 'b', 'c']
in (3) # for i in (3): print(i) # Error
f’{}’ # print(f'Curly brackets: {}') # Error
print(50 and 100) # 100
add() # set1 = {1, 2, 3}; set2 = set1.add(4); print(set2) # None # print({1, 2, 3}.add(4))
print(11 > 0 is True) # False
```

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

Actions: 

Navigation
```python
goto() # page.goto("https://www.demoblaze.com/")
reload # page.reload

Interaction
```python
click() # page.click("id=login2")
locator() # page.locator("id=login2").click()
```
Text input
```python
fill() # page.locator("[name=country]").fill("Russia")
```
Verification
```python
expect() # expect().to_have_title() # expect(page).to_have_title("Google")
.to_have_title() # expect(page).to_have_title(re.compile("text"))
.toHaveCSS # expect(page.locator("#zip-code")).toHaveCSS("background-color", "rgb(248,215,218)")
```

### <a id="QA">QA</a>
[home](#home)

### <a id="TDT">TDT - Test Design Techniques</a>
[home](#home)

1. Классы эквивалентности (диапазоны, 1)
2. Граничные значения (границы, 1-2-3)
3. Причинно-следственный анализ (карта причин и откликов)
4. Прогнозирование ошибок (негативные тесты)
5. Попарное тестирование (pair-wise, 3x3, 9 vs 27)
6. Диаграмма состояний (диаг сост типа флоу Jira)
7. Таблица принятия решений (decision table, Pos&N х T/F = Results)

#1 Классы эквивалентности, реальные диапазоны значений, берем по одному значению
#2 Граничные значения (“брат” КЭ), берем значения на граница и в шаге до и после
#3 Причинно-следственный анализ
#4 Прогнозирование ошибок
#5 Попарное тестирование (pair-wise) https://pairwise.teremokgames.com/
#6 Диаграмма состояний
#7 Таблица принятия решений (decision table, T/F, Pos&N + Results)

### <a id="Int">Interview</a>
[home](#home)

### <a id="Ach">Achievements</a>
[home](#home)
me/me
- ROR dev: Re-run ASAP > QA Aut want > higher priority added
- ROR dev: Re-run ASAP & create bak > Devs want > even higher priority & backs added
- PS dev: Logs & baks clean-up > Massive tests filled shares > CI/CD task added (daily-nightly)
- ROR-JS dev: srv which should not schedule did, iscala had a lot of necessities, their portal was much complex, also supported a lot of very complex requests from in, they wanted to draw tables, a lot of info for mongo db + portal visials should be adjusted for their products.
- ROR-JS-SVG: funny results with 3 colour pie diagrams, whole saturday
- ROR dev: results > QAs want to send info to devs > Envelop icon opens Outlook ()
- Portal results less clicks > QAs want to analyze results faster > P draws icons using result stats
- Execute Web S 1by1 > QAs told W results are too big >
- AUT+IT: 1ms timeouts > new ssd > measured we can go 1ms, rebalanced vms, changed how dbs were restored from regular to snapshots, x2 lifetime, from 16gb to 8gb disk wr per restore
- Cloud VMs On/Off, cust & part needed vms when we were offline, AZ sched was not working properly, so I created tasks in ci cd to shut down and start up vms when needed
- Cloud VMs RDS grace period 120d, vms were very hard to setup, no way to use templates or setup RDS server in cloud, I worked to find colution & finally did, PS file was resetting grace period
- Monitoring Build/Infra team, bad builds were not an issue, but also file delivery was pure, I monitored all issues & saved\parsed additional logs for yearly report to their boss. I did a great job for whole company, finfing a tons of infra and dev bugs immediately, thats why when we were absent quality is drocode pping
- Tutored a lot of colleagues, up to 30 folks on education sessions
- Tech support for utilities, portals all by myself & a lot of assistance to other depts (qms, scala ERP with cloud, called MS) no one was helping
- other ERP dpt had issues with Azure, helped them with perf testing and to get proper config from MS, set up and moved their vms from us to them
- msk devs wanted all sorts of msgs to mail and  IM is something fails or passes, all requests were satisfied, we used hooks in tfs
- helped us, mx and in dept to setup sending out results to my portals
- all reports were compiled by me, others wrote autotests
- our aut utility was tested\benchmarked\supported solely by me,manual, aut and extensive 400 hours autotests by me when situation allowed comparing exec time for suites, documentation and help review with IT writers team
- test complete required parsing all info from logs, so that autotesters do not need to open huge logs, at the time of failure they returned some info which could not be easily obtained later + xml parsing.
- our aut utility participated on most discussions with devs (3 devs)
- retesting was easy due to advanced scheduling  system, autotesters were happy, 2 priorities, was a bit difficult but i did it
- node.js helped to setup web environments for autotetsers and aut vms
- setuped test complete vms with licenses resolved all issues with other depts
- monitored expenses, found reasons why costy, reported to managers (1+1+4)
- ubuntu + mongod solely mine area, all setup and infra, indexes in mondod speeded up 20-30 time some sneaky large report loved by some autotesters
- worked with IT trying to optimize load (later in Austin vms were managed automatically)
- connect to 40 vms at once not an issue royal ts, this was also helped to test iScala rdp_rds connections
- antivirus issues also resolved by me, 450 vms, later was helping Marina with her vms
- all tickets to IT were sent via me & I contacted with them, ips, issues, rights, if any issues with vms I helped to investigate
- cloud setup & admins & MS also mine part (but for TFS we had other admin, he backed up db)
- kept an eye on devs of fws which we got TS & wdio\protractor, often we were finding issues (ate\ewa ours, ts in, wdio mx)
- other autotesters helped with code coverage sometimes i had no free time
- tight communication with usmx in aut depts solely me, exch of exp and resolving issues (erp was installed in 3 different ways lol)
- fixing scripts, last years when many were fired, moved vms to austin and setupped\recreared working with it and infra team
- 20+ managers, 20+ depts in touch
- + a lot of interesting things, code base should be checked.


![image](https://github.com/otomakine/KB/assets/29117632/6c88c964-a73e-4e10-b95f-f65cac0fc631)

### <a id="Fail">Failures</a>
[home](#home)
- Portal halted & AZ Queue sent/lost all results > Parsed logs in cold blob & re-sent results to Portal (logs had JSONs)

### <a id="EndQs">Interview Ending Questions</a>
[home](#home)
Завершение интервью - свои вопросы
- Что ожидается от сотрудника в первое время, какие метрики?
- Как появилась вакансия, что не устроило в прошлом сотруднике?
- Если вы бы меня наняли как бы вы поняли через год что вы сделали правильный выбор?
- Какой процент автоматизации и в какие команды ищете автоматизаторов?
- Почему ищете кого-то на эту вакансию, что произошло с прежним работником?
- Спросить что-то интересное о себе и о чем с удовольствием расскажут (напр. что крутого команда сделала за последнее время)
- Какие планы у отдела на полгода-год
- Какие планы на меня на сл год-два, какие технологии и фрейм ворки, как часто релизы и как быстро чекины комитятся, много ли легаси
- Какие грейды у членов команды, сколько человек, кто руководитель, с какими отделами общаться
- Есть ли дежурства
- Куда идет компания, что будем делать через 10 лет, как взорвем рынок
- Как устроено перформанс ревью, какие метрики, какие скилы оцениваете, годовые обзоры
- Как происходит пост обучение сотрудников, курсы, планы развития
- Что делаете когда не укладываетесь в спринт?
- Какие технологии используете, как происходит процесс взаимодей

