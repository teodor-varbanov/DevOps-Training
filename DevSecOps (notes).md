##SEC

- (MS) Secure Development Lifecycle
    - Requirements, standarts and frameworks
    - Analysis, security baseline
    - Secure Design Principles, controls and monitoring
    - Security practices and training, hardening and secure code review
    - Security testing, bug handling
    - Patch management, library upgrades, monitoring

- Security is everyone's responsibility
- Prevention is the key to avoiding problems
    - Обученията са форма на prevention

- Sec trilemma: functionality, security, usability

- Availability, integrity, confidentiality

Phases
- Detection
- Analysis
    - determine where the threat originated, that will detect how to move forward. Often, rebuilding from scratch will be needed, especially if the base has been compromised
- Isolation
    - infrastructure, network, IaM (cloud). Availability may be impacted, but that's fine.
- Eradication
- Post-mortem

##DevSecOps

- Няма едно единствено тълкувание за това какво е DevSecOps - в различни компании, структурата е разлина
- SecOps много често нямат Dev опит, съответно не разбират Dev lifecycle в дълбочина
- Най-често: DevOps + SecOps = DevSecOps
- DevOps задължително съдържа в себе си DevSecOps, защото е екипът който разбира DevOps процесът в дълбочина

#Основни компоненти:
- App/API инвентар
    - Повечето съвременни библиотеки имат собствени механизми за защита
    - Въпреки това трябва да се следят изкъсо dependancy-тата на кода ни и да пускаме чест анализ (мониторинг)
- Custom code security 
- Одити и пен тестове 

- Автоматизацията, както е с IaaC, елиминира човешката грешка и улеснява налагането на Sec framework (и го прави по ефикасно)
    - Трябва да се експериментира - става с vulnarable by design приложения
- Sec трябва да се премести максимално на ляво, т.е. максимално рано в dev process-a
    - Освен, че всичко е по-сигурно по този начин, това спестява и много усилия и потенциално двойна работа

- Ако не идва от всички страни - няма да стане
    - всички трябва да са наясно с това какви са изискванията
- Всяка една стъпка трябва да има security check, от първата нататък
- Трябва да автоматизираме всичко
- МОНИТОРИНГ! Ако не го сканираме ние, някой друг ще го сканира.

DevSecOps, като DevOps = culture + tools

#Defence in depth
- множество редундантни defence measures
- различни контроли на всеки слой

##**OWASP**

SAST - статичен анализ на кода
DAST - динамичен: симулира атака, търси мисконфигурации, injections и т.н. 
    - DAST инструментите се хранят с предварително написани test cases 
IAST - интерактивен сек тестинг: търси privilage escalations, network requests и т.н.
RASP - рънтайм протекция: следи вече деплойнати на прод апликации, включително наблюдава custom build libraries
SCA 

**SNYK** върши всичко от гореизброените

- Във всяка стъпка на пайплайна трябва да има интегрирано сканиране


##TOOLS:
- OWASP ZAP - free, но много false positives 
- snyk
- trivy
- terragoat - vulnerable by design terraform приложение

Инструментите трябва да се тестват и трябва да се види до колко забавят pipeline-a. 

Sidenote: xssgame - браузър игра в която могат да се тестват пейлоудове. 
Sidenote: струва си да се ползват горепосочените dummy apps за тестване на различни тулове
