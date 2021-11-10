# Secure Coding

## 1. Security Design

Beveiliging moet meegenomen worden in het ontwikkelproces:

-   Geschatte kosten van beveiligingsproblemen in 2017: 3.5 miljoen per breach;
-   Maximale boete onder AVG: Hoogste van 20 miljoen of 4% van de wereldwijde omzet;

### 1.1 CIA:

In het centrum van informatiebeveiliging is information assurance: Het behouden van **Confidentiality**, **Integrity** and **Availability** (CIA) van informatie.

#### 1.1.1 Confidentiality

-   Vertrouwelijkheid;
-   Gegevens mogen alleen door geauthoriseerde gebruikers ingezien worden;
-   Privacy is hieraan verwant: Confidentiality is dan ook een onderdeel van privacy;

Een aanvaller zou dit kunnen schenden door bijvoorbeeld **Eavesdropping**:

-   Aanvaller luistert passief mee met verkeer tussen partijen;
-   Ook wel Snooping, snuffing of wiretapping genoemd;
-   Mogelijke oplossing: Encryptie (**HTTPS** bijvoorbeeld);

#### 1.1.2 Integrity

-   Integriteit;
-   Gegevens mogen alleen door geautoriseerde personen gewijzigd worden;
-   Onafhankelijk van confidentiality: Aanvaller kan blind wijzigingen aanbrengen;

Een aanvaller zou dit kunnen schenden door bijvoorbeeld **Man-in-the-middle**:

-   Aanvaller onderschept verkeer tussen de twee partijen;
-   Lijkt op **Eavesdropping** maar hierbij is de aanvaller actief;
-   Verkeer kan optioneel worden aangepast, potentieel zelfs zonder dat de aanvaller het verkeer kan lezen;
-   Mogelijke oplossing: Digitale handtekening (**JWT** bijvoorbeeld);

#### 1.1.3 Availability

-   Beschikbaarheid;
-   Het systeem moet beschikbaar zijn als geautoriseerde gebruikers het willen gebruiken;

Een aanvaller zou dit kunnen schenden door bijvoorbeeld **Denail of service**:

-   Aanvaller voorkomt dat partijen kunnen communiceren;
-   Distributed Denail of service;
-   STN-flood: Berichten met ongeldig IP-adres zorgen dat de server poorten reserveert en daardoor niet meer bereikbaar is;
-   Mogelijke oplossing: Firewall;

#### 1.1.4 Non-repudiation (extra)

-   Onweerlegbaarheid;
-   Zowel zender als ontvanger mogen niet kunnen ontkennen dat een bericht verstuurd of ontvangen is;
-   Voorbeeld: Hantekening op contract;
-   Niet technisch maar juridisch;
-   Mogelijke oplossing: Blockchain;

### 1.2 Principes van secure design

Richtlijnen om betere keuzes te maiken bij het ontwerpen van secure systems:

-   Least privilige (in code):
    -   Geef elke operatie zo min mogelijk rechten;
    -   Door te ruime rechten kan een aanvaller toegang krijgen tot beschermde informatie;
    -   Voorbeeld: Elk proces op een server draait onder zijn eigen gebruiker met beperkte rechten;
-   Compartimentaliseren (in systeem):
    -   Rechten en verantwoordelijkheden gescheiden houden;
    -   Impact van een hack beperken;
    -   Duidelijker wat verschillende onderdelen doen;
    -   Voorbeeld: Rechten van beheerders beperken tot de module die ze beheren;
-   Vertrouw derde partijen niet:
    -   Derde partijen mogen nooit vertrouwd worden;
    -   Invoer moet gecontroleerd worden;
    -   Credentials van derde partijen moeten gecontroleerd worden;
    -   Gebuik wachtwoorden, client certificates, etc.;
    -   Voorbeeld: Invoer van gebruikers moet gecontroleerd worden op aanvallen:
        -   Webformulieren;
        -   Bestanden;
        -   GUI-velden;
        -   Externe API's;
        -   Database;
        -   Andere applicaties;
-   Keep it simple, stupid:
    -   Ontwerp een systeem om zo simpel mogelijk te zijn;
    -   Als developers niet begrijpen hoe het systeem werkt kan dat leiden tot kwetsbaarheden;
    -   Simpel ontwerpen is niet makkelijk!;
    -   Voorbeeld: Geen complexe configuratietaal implementeren als die niet nodig is;
-   Loggen:
    -   Houd een audit log bij van alle securitygebeurtenissen;
    -   Het log moet beschermd worden tegen ongeautoriseerde wijzigingen;
    -   Mogelijk om naderhand te controleren of en hoe er iets fout is gegaan;
    -   Voorbeeld: Houd een audit log bij van alle bewerkingen op gevoelige tabellen;
    -   Wat moet je loggen:
        -   Tijd;
        -   Severity;
        -   Applicatietoestand;
        -   Welke feature gebruikt wordt;
        -   Sessieinformatie;
        -   Foutcondities (excepties, databasefouten);
    -   Wat moet je niet loggen:
        -   Sessie ids;
        -   Wachtwoorden;
        -   Persoonlijke gegevens (AVG);
        -   Gevoelige gegevens zoals creditcardnummers;
-   Fail safe:
    -   Foutcondities moeten zo afgehandeld worden dat het systeem veilig blijft;
    -   Fouten mogen niet leiden tot ongeautoriseerde toegang;
    -   Zorg dat de defaultinstellingen van de applicatie veilig zijn;
    -   Let op confities rond excepties;
    -   Voorbeeld: Gebruik een whitelist in plaats van een blacklist;
-   Geen security through obscurity:
    -   Ga ervan uit dat een aanvaller alle algoritmes kent;
    -   Verborgen houden van algoritmes is moeilijk;
    -   Bekende algoritmes zijn mogelijk ook beter getest door experts;
    -   Wachtwoorden en sleutels vallen hier niet onder (SHA, JWT);
    -   Voorbeeld: Maak geen gebruik van 'magische' URL's voor veiligheid;
-   Defense in depth:
    -   Vertrouw niet op een enkele laag veiligheid;
    -   Geen enkel systeem is perfect;
    -   Zorg dat elke laag in het systeem beveiligd is;
    -   Voorbeeld: Voer access control uit in alle lagen van de applicatie: IO, services en database;
-   Bestaande securitytechnologie:
    -   Gebruik beproefde technologie voor beveiliging;
    -   Securitytechnologie bouwen is heel specialistisch werk;
    -   Je bent vast best slim, maar hackers zijn ook slim en er zijn er een stuk meer van;
    -   Maak gebruik van industriestandaarden;
    -   Voorbeeld: Schrijf niet zelf een SSO library maar gebruik bestaande technologie;
-   Beveilig de zwakste schakel:
    -   Zoek de zwakste schakel in jouw systeem in bevelig die;
    -   Kijk welke bedreigingen er zijn;
    -   Voorkom systemen waar alleen de voordoer goed beveiligd is;

## 2. Security Vulnerabilities

Een lijst met bekende kwetsbaarheden in frameworks en applicaties valt te vinden op:

-   https://cve.mitre.org/
-   https://cvedetails.com/

### 2.1 Buffer overflow

-   Een applicatie probeert meer data te schrijven dan waarvoor ruimte gereserveerd is;
-   Doet zich voornamelijk voor in talen zoals C en C++ waar je zelf ruimte moet reserveren;
-   Talen als Java en PHP zijn niet rechtstreeks kwetsbaar, maar de JVM of PHP-interpreter kan wel kwetsbaar zijn;
-   Kan de applicatie laten crashen, of als de geschreven data goed gekozen is, arbitraire code laten uitvoeren;

Een voorbeeld is de stack buffer overflow:

-   De overflow vindt plaats in de stack;
-   Hier staat onder andere de return pointer van de functie;
-   Deze pointer kan overschreven worden en gepoint worden naar code van de boosdoener;

```C
void foo (char *bar) {
    char c[12];
    strcpy(c, bar); // Geen controle op lengte van invoer.
}

int main (int argc, char **argv) {
    foo(argv[1]);
    return 0;
}

argv[1] = "AAAAAAAAAAAAAAAAAAAAAAAA\x08\x35\xC0\x80"
```

-   Oplossing ligt deels in mitigatie door het besturingssysteem (defense in depth);
-   Overflows kunnen soms gedetecteerd worden;
-   De stack kan niet-executable gemaakt worden;
-   De geheugenadressen in de stack kunnen gerandomiseerd worden;

### 2.2 SQL injection

-   Kwetsbaarheid waarbij een aanval arbitraire SQL kan laten uitvoeren door een database;
-   Meest voorkomende kwetsbaarheid op het web;
-   Data kan onterecht uitgelezen, gewijzigd of verwijderd worden;
-   Oorzaak: Gebruik van niet-vertrouwde data;
-   Oorzaak: Mengen van data en code;

```Java
String name;
Connection conn;
conn = DriverManager.getConnection("jdbc:...");
Statement stmt = conn.createStatement;
stmt.executeUpdate("INSERT INTO Students (name) " + "VALUES ('" name + "');");
```

Het resultaat van deze Java code:

```SQL
INSERT INTO Students (name)
VALUES ('Robert'); DROP TABLE Students; --')
```

Oplossing:

-   Onveilige karakters escapen:
    -   Bijvoorbeeld door backslash of verdubbelen;
    -   Beter dan niets;
    -   Code wordt afhankelijk van specifieke database-implementatie;
    -   1 keer vergeten is genoeg om kwetsbaar te zijn;
    -   Onderliggende probleem wordt niet opgelost: Code en data worden vermengd;
-   Precieze regels afhankelijk van het SQL-dialect;
-   Dit voorbeeld is voor MySQL;

```Java
stmt.executeUpdate("INSERT INTO Students (name) " + "VALUES ('" escape(name) + "');");

String escape(String s) {
    s = s.replace("'", "\\'");
    ...
    return s;
}
```

```SQL
INSERT INTO Students (name)
VALUES ('Robert\'); DROP TABLE Students; --')
```

Wat je toe kan passen is Least Privilige:

-   Database-accounts met alleen leesrechten zijn minder kwetsbaar;
-   Data kan nog steeds gelezen worden. Database-accounts per tabel zouden dit weer deels kunnen verhelpen;

Prepared Statements is beter:

-   Techniek waarbij de query met placeholders in plaats van variabelen geschreven wordt;
-   Query plan wordt gebaseerd op deze abstracte query;
-   Database kent hierdoor het onderscheid tussen code en data;
-   Extra voordeel: Sneller bij herhaaldelijk gebruiken van gelijkende query's;

```Java
String name;
Connection conn;
conn = DriverManager.getConnection("jdbc:...");
Statement stmt = conn.createStatement;
stmt.executeUpdate("INSERT INTO Students (name) " + "VALUES (?);");
stmt.values(name);
```

### 2.3 Cross-site scripting

-   Aanval waarbij niet-vertrouwde data getoond wordt zonder verdere controle;
-   Lastiger te voorkomen den SQL injection;
-   Oorzaak: Gebruik van niet-vertrouwde data;

Er zijn 2 varianten:

-   Reflected XSS:
    -   De payload wordt per aanval meegegeven in de request (query string of POST-body);
    -   Voorbeeld: Een zoekpagina die de gezochte tekst toont;
    -   Sommige browsers hebben hier gedeeltelijke bescherming tegen;
-   Stored XSS:
    -   De payload wordt in een database opgeslagen en bij elke request getoont;
    -   Voorbeeld: Een forumpagina die opgeslagen posts toont;
    -   De payload kan makkelijker gevonden worden door de beheerder;

Voorbeeld:

```Javascript
var name = "<script>alert(1);</script>";
return "<h1>Hello, " + name + "</h1>";
```

Oplossing is net als bij SQL injection bijvoorbeeld escapen:

-   Name zou alleen tekst mogen zijn;
-   Oplossing voor HTML is bijvoorbeeld alleen gegarandeerd veilige karakters laten staan en andere karakters als entity tonen;
-   Om tekst veilig te kunnen gebruiken in Javascript zijn andere escapingregels nodig;
-   Er is geen gegarandeerd mechanisme zoals prepared statements alleen frameworks hanteren het wel vaak standaard;

Daarnaast kunnen we ook blacklists/whitelists gebruiken en de HTML sanitzen. Vaak doen frameworks dit voor je.

Browsers beschikken tegenwoording over Same-origin Policy:

-   Beschermlaag in de browser;
-   Data van verschillende origins blijft gescheiden:
    -   Protocol moet het zelfde zijn;
    -   Domein moet hetzelfde zijn;
    -   Port moet hetzelde zijn;
-   Voorkomt requests naar andere origins waar je misschien al ingelogt bent.

Toch kan dit omzeilt worden.

Content Security Policy is ook een slimme implementatie:

-   HTTP-header die een policy definieert om te bepalen welke scripts en andere resources gebruikt mogen worden;
-   Mogelijkheid om een whitelist op te stellen van geldige scripts, andere scripts kunnen dan niet uitgevoerd worden;

### 2.4 Cross-site request forgery

-   Een request uitvoeren naar een site vanuit een andere site zonder instemming van de gebruiker;
-   Cookies worden meegestuurd naar de andere site, dus de request heeft de complete rechten van de gebruiker;

```HTML
<form method="post" action="https://.../admin/roles">
    <input type="hidden" name="userId" value="1">
    <input type="hidden" name="execute" value="on">
    <input type="submit" value="Download Free MP3s!">
</form>
```

-   Als de gebruiker nog was ingelogd op de aangevallen website worden de cookies automatisch meegegeven;
-   De aanvaller hoeft de cookies niet te hebben;
-   De aanvaller hoeft niet eens bij de server te kunnen;
-   Als de aanvaller de cookies wel heeft, bijvoorbeeld via XSS, kan hij de request ook zelf doen.
-   De gebruiker hoeft niet eens een actie te ondernemen. Forms kunnen automatisch verzonden worden;
-   Dit kan niet via AJAX, dat wordt geblokeert omdat het een ander domein is.

Oplossing is een Synchronizer token pattern:

-   Maak per sessie of per formulier een uniek willekeurig token (CSRF-token) aan dat als hidden input aan het formulier wordt toegevoegd;
-   Controleer of de tokens overeenkomen bij het versturen van het formulier;
-   De aanvaller kan het token niet verkrijgen omdat hij het resultaat van requests nooit te zien krijgt;
-   Dit kan (deels) gautomatiseerd worden via een middleware-laag of filter in veel frameworks;

Een andere oplossing is een challenge/response pattern:

-   Als de gebruiker een gevoelige actie uitvoert moet hij zich opnieuw authenticeren;
-   Webwinkels gebruiken dit wel: Je kan met je opgeslagen sessie wel rondkijken en je winkelwagentje vullen, maar bij het bestellen heb je je wachtwoord nodig;
-   Voorkomt CSRF omdat de authenticatie altijd expliciet door de gebruiker gedaan moet worden;

## 3. Secure software development (gastcollege)

### 3.1 OWASP

Open Web Application Security Project, contains:

-   Top 10 risks:
    -   **A01:2021-Broken Access Control:**
        -   Get access to resources by manipulating input;
        -   Do's:
            -   Central authentication mechanisms;
            -   Disable unauthenticated access to any resource;
    -   **A02:2021-Cryptographic Failures:**
        -   Get access to data because it is not encrypted in transit and/or rest;
        -   Do's:
            -   Encrypt transport of data (HTTPS, secure mail, ...);
            -   Not use weak crypto keys such as SHA1;
            -   Use a salt to encrypt stored passwords;
            -   Do not put sensitive data in caches;
    -   **A3:2021-Injection:**
        -   Get access to resources by manipulating unput;
        -   Do's:
            -   Don't ever use an un-sanitized user input in any command/query;
            -   Ensure running with least privilige;
            -   Set httpOnly flag to cookies to prevent stealing it from scripts;
            -   Proper escape (untrusted input) data in the oytput (XSS);
    -   **A4:2021-Insecure Design:**
        -   Missing or ineffective control design;
        -   Do's:
            -   Thread modeling;
            -   Secure Software Development Lifecycle (SSDLC);
            -   Consider leveraging the OWASP Software Assurance Maturity Model (SAMM);
    -   **A5:2021-Security Misconfiguration:**
        -   Don'ts:
            -   Unnecessary features are enabled or installed (e.g., ports, services, pages, accounts or privileges);
            -   Default accounts and their passwords are still enabled and unchanged;
            -   Copy code from internet without thinking;
        -   Do's:
            -   Prevent any manual installation actions;
            -   Use layering in the infrastructure;
            -   Implement monitoring and alerting;
    -   **A6:2021-Vulnerable and Outdated Components:**
        -   Get access to resources by exploiting vulnerabilities;
        -   Do's:
            -   Subscribe to security bullitins;
            -   Constant patching of all components;
            -   Remove unused dependencies;
            -   Obtain components from trusted sources;
            -   Monitoring and alerting;
    -   **A7:2021-Identification and Authentiation Failures:**
        -   Get access to resources by guessing/stealing passwords or stealing sessions;
        -   Do's:
            -   Multifactor login;
            -   Sessions should expire;
            -   Passwords should be properly encrypted;
            -   Prevent brute force;
    -   **A8:2021-Software and Data integrity failures:**
        -   An insecure CI/CD pipeline can introduce the potential for unauthorized access, malicious code or system compromise;
        -   Do's:
            -   Use digital signatures or similar mechanisms to verify the software or data is from the expected source and has not been altered;
            -   Ensure libraries and dependencies, such as npm or Maven, are consuming trusted repositories;
            -   Ensure that there is a review process for code and configuration changes;
            -   Ensure that your CI/CD pipeline has proper segregation, configuration and access control;
    -   **A9:2021-Security Logging and Monitorying Failures**:
        -   Get time to hack because no alarm bells are rining (on time);
        -   Do's:
            -   Ensure all user actions to high value information is audited;
            -   Ensure effective monitoring and alerting is in place of suspicious activities;
            -   Establish an incident response and recovery plan;
    -   **A10:2021-Service Side Request Forgery (SSRF)**;
-   ASVS (Application Security Verification Standard Project);
-   Cheat sheets;
-   Test scenario's;
-   Presentations and examples;

### 3.2 GDPR

Sanctions:

-   A warning in writing incases of first and or non-intentional non-compiance;
-   Regular periodic data protection audits;
-   For small infringement: A fine up to 10M EUR or u to 2% or the annual income;
-   ...;

What is defined as personal data?: Personal data is defined as any information relating to an identified or identifiable natural person.

Rules:

-   Transparency: You have to expain in an understandable way how the data is collected and processed;
-   Data transfer: Citizens can transfer their data from one service provider to another;
-   Right to be forgotten: When a person asks your company to delete the personal data, you are obliged to do so;
-   Reporting duty: Is there a data breach? You're obliged to report this within 72 hours, unless you can prove that it does not endanger the personal data;

How to handle personal data:

-   Only store data that is needed;
-   Use technical keys for correlations;
-   Never use production data for testing;
-   ...;

## 4. Access Control

### 4.1 Authenticatie

Wie ben je?

HTTP is stateless, login informatie moet ergens worden opgeslagen: (sessie)cookies.

#### 4.1.1 Registratie

-   Altijd via HTTPS!;
-   Gebruikersnaam, e-mail, wachtwoord;
-   E-mailadres controleren;
-   Automatische registratie voorkomen: CAPTCHA's (vrij zwak), timeouts, honeypotveld;
-   Honeypotveld: Onzichtbaar veld voor de gebruiker dat, als het ingevuld wordt, de registratie als automatisch beschouwd en negeert;

#### 4.1.2 Inloggen

-   Altijd via HTTPS!;
-   Geen aparte foutmeldingen voor fout in gebruikersnaam of wachtwoord;
-   Niet obeperkt laten proberen om aanvallen tegen te gaan;
-   Dit kan wel een **denail of service** attack mogelijk maken;
-   Gebruikers opnieuw laten inloggen voor gevoelige operaties;

#### 4.1.3 Hashing

-   Wachtwoorden nooit opslaan als plaintext!;
-   Wachtwoorden opslaan via one-wayfunctie, een hash;
-   Hashes hebben standaard lengte, ongeacht lengte van het wachtwoord;
-   Het wachtwoord kan in principe niet berekend worden uit de hash;
-   Een wachtwoord kan wel vergeleken worden met een hash;
-   Wachtwoorden ook vergelijken als gebruikersnaam fout is om **timing attacks** te voorkomen;

Aanvallen op hashing:

-   **Brute force attack**: Alle mogelijke wachtwoorden proberen;
-   **Dictionary attack**: Meer waarschijnlijke wachtoorden eerst proberen;
-   **Rainbow table**: Lijst met een wachtwoord voor elke mogelijke hash;

Hashing verbeteren:

-   Salt: Een willekeurige waarde die aan het wachtwoord wordt toegevoegd zodat gelijke wachtwoorden andere hashes krijgen;
-   Pepper!;
-   Iteraties: Veel hashalgoritmes kunnen langzamer gemaakt worden door meer iteraties van het algoritme uit te voeren, hierdoor wordt aanvallen lastiger;

MD5 en SHA1:

-   Message Digest Algorithm 5;
-   Secure Hash Algorithm 1;
-   Deze zijn beide te snel: Brute force attacks zijn relatief makkelijk uit te voeren;
-   Secundair zijn er ook een aantal bekende collision attacks;
-   Bottom line: MD5 en SHA1 zijn niet geschikt voor enige vorm van informatiebeveiliging;

PBKDF2, bcrypt en scrypt:

-   Password-based key derivation function;
-   Ontworpen om lanzaam te zijn en nog langzamer door hoge iteration counts;
-   PBKDF2 is makkelijk te implementeren in GPU's dus niet optimaal door wachtwoorden;
-   Bcrypt is efficiënt te implementeren in custom hardware (FPGA) dus ook niet optimaal;
-   Scrypt is nieuwer, dus misschien zitten er nog kwetsbaarheden in;

Slim:

-   Hash in wachtwoord opslaan;
-   Wachtwoord met betere hash updaten zodra nieuwe uit is, wachtwoord migraten;
-   PHP doet dit, voorbeeld!;

### 4.1.4 Cookies

-   Client side;

### 4.1.5 Sessies

-   Server side;

### 4.2 Access control/Autorisatie

Autorisatie:

-   Wat mag de gebruiker;
-   Afhankelijk van de gebruiker;
-   Afhankelijk van de actie;
-   Standaard hebben gebruikers geen rechten;
-   Rechten kunnen afhankelijk zijn van externe factoren zoals locatie of tijd;

Do's:

-   Implementeer AC op een centraal punt;
-   Zorg dat de regels voor access control flexibel zijn;
-   Gebruik geen informatie uit een HTTP request;
-   Zorg dat AC niet bestaat uit moeilijk te raden URL's;
-   Wijzigingen in rechten moeten meteen worden doorgevoerd, niet pas bij de volgende login;

Role based:

-   Gebruikers hebben niet rechtstreeks rechten op objecten;
-   Rollen hebben rechten op objecten;
-   Gebruikers kunnen één of meer rollen hebben;
-   Beperking: Rollen zijn globaal terwijl je in de praktijk echter vaak context-afhankelijke rollen wilt: Een gebruiker msg wel zijn eigen blogposts bewerken maar niet die van een ander;
-   Beperking: Rollen controleren maakt aanpassen rechten lastig;

Permission based:

-   Controleer permissies in plaats van rollen;
-   Permissies kunnen informatie over het object coderen, bijvoorbeeld de id van een blogpost;
-   De permissies worden centraal gekoppeld aan de rollen;
-   Bij het koppelen kan context meegenomen worden;

### 4.3 Gegevensbeveiliging

-   Gegevens kunnen in meerdere toestanden bestaan;
-   ...;

#### 4.3.1 Encryptie

-   Gegevens versleutelen zodat deze alleen met een sleutel gelezen kunnen worden;
-   Data at rest beveiligen zodat alleen bevoegde gebruikers dit kunnen lezen;
-   Beveiligt tegen ongeautoriseerde toegang of diestal;
-   Wetgeving zoals AVG kan dit verplicht stellen;

#### 4.3.2 Cryptografisch ondertekenen

-   Oorsprong van bericht controleren;
-   Handtekening toevoegen: Versleutelde hash van bericht;
-   Ontvanger kan hierdoor zien dat alleen de bezitter van de sleutels het bericht kon versturen;
-   Een aanvaller kan zijn eigen bericht niet ondertekenen, maar wel een onderschept bericht opnieuw versturen (replay attack);

#### 4.3.3 Symmetrische encryptie

-   Dezelfde sleutel wordt gebruikt bij versleutelen en ontsleutelen;
-   De sleutel moet geheim blijven;
-   Caesar, Enigma, XOR, AES, DES, ...;
-   Niet geschikt voor cryptografisch ondertekenen;

#### 4.3.4 Assymetrische encryptie

-   Verschillende sleutels voor versleutelen en ontsleutelen;
-   Één sleutel is publiek, de andere sleutel is geheim (private);
-   Publieke sleutel gebruiken voor versleutelen: Alleen de eigenaar van de geheime sleutel kan ontsleutelen;

#### 4.3.5 Transport Layer Security (TLS)

-   Protocol om data in transit te beveiligen, bijvoorbeld over HTTP(S);
-   Opvolger van Secure Socket Layer (SSL);
-   Meedere versies: Gebruik minimaal TLS 1.1;
-   Verbinding is veilig omdat de inhoud versleuteld wordt;
-   De identiteit van de verzender is bekend omdat het beriht ondertekend wordt;
