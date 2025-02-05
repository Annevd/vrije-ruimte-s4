# Inhoudsopgave

  - [Algemene informatie](#algemene-informatie)
  - [GIT & Bitbucket](#git--bitbucket)
  - [Formulieren API](#formulieren-api)
  - [Lokaal een project clonen met SSH](#lokaal-een-project-clonen-met-ssh)
  - [3/02](#3-februari-2025)
  - [4/02](#4-februari-2025)
  - [5/02](#5-februari-2025)
  - [6/02](#6-februari-2025)
  - [7/02](#7-februari-2025)

## Algemene Informatie

### Wekelijkse meetings:
  - Elke dag:
    - 9:15: Daily standup (US Media)
    - Project team standup (Team)
  - Elke vrijdag:
    - 16:30 US Presents 
  - Elke 3 weken:
    - 9:30 CLOMP Team standup
    - 15:00 Voorbereiding CLOMP voor vlg week

**Daily standup:**
- Korte samenvatting van de vorige werkdag
- Wat ga je vandaag doen?
- Zijn er nog “roadblocks”?
- Is er nog iets “te vieren”?

**Daily projectteam standup:**
- Specifieker de tasks bespreken
- Waar loop je tegen aan?

**CLOMP voorbereiding:**
- Wat gaan we doen? Wat staat er?
- Inschatten
- Toetsen (haalbaar?)
- Verdelen

### Tools:

**Communicatie & planning:**
  - Slack
  - Gmail
  - Google meet
  - Google drive
  - Planningsbord
  - Forecast: online planning
**Productiviteit:**
  - Linear: agile project management tool
  - Youtrack: tickets systeem voor service en planningsbord (klanten zitten hier ook in)
  - BitBucket: GIT
  - Sonarcloud: code kwaliteit analyse
  - Keyring: wachtwoorden manager
  - Slite: de US wiki

### Tech stacks:

  - Back-end:
    - Angular
    - NestJS
    - NodeJS
  - CMS:
    - Wordpress, PHP based
    - Contentful, NodeJs
  - Front-end:
    - HTML5/CSS3
    - Javascript/Typescript
    - Progressive Web App Standards
    - JSON/Rest API’s

---

## GIT & Bitbucket

We use git to manage our code and Bitbucket as our version control manager.

### Workflow
We use a workflow which is similar to the Git workflow. Usually you create a feature or hotfix branch from master. The `master` branch usually is the branch that is on production/live. We branch from master so features can be released separately. You can only push to develop and master via a pull request.

### Naming of branches.
Use either `hotfix/` or `feature/`, depending on the type of issue or project. For some flows we also use `release/`  (see deployments a bit further down). If it's an issue from Youtrack use the issue nr as the branch name. For instance `hotfix/SDN-1745`. When you're done fixing your bug or creating your feature, you create a pull request to develop. You can add a reviewer so another developer can check your code. Once the Pull Request is merged it starts a pipeline.

We use git to add, commit, push etc.  If you don't know how to do this, you can do this online training, it won't take that long.

### Deployment & Pipelines

We use bitbucket pipelines to trigger build, scan and deployment processes.
For some projects (mostly SIDN projects) we use bitbucket deployments to deploy our code. For other projects we use a simpler deployments process. "Develop" get build and deployed to Staging. "Master" gets build and deployed to Production/Live. Sometimes there's also an Accept branch which get build and deployed to Accept. For this way of deployment the code gets build anew for every environment.

- [Handige site om GIT basics te leren](https://learngitbranching.js.org/)
  
---

## Formulieren API

**API:** Communiceren tussen de frontend en backend servers

Bijvoorbeeld postcode.nl

**REST API:** Hoe definieer je de endpoints (url waar tegen je praat)

[staging.api.terredeshommes.nl/docs](staging.api.terredeshommes.nl/docs) voor documentatie over een API van Terredeshommes.

Met SQL kan je data uit een database halen.

Een _ORM_ creëert een "virtuele object-database" die de developer kan gebruiken om gegevens op te halen, te wijzigen of te verwijderen, alsof het objecten in het programma zelf zijn. Hierdoor hoeft de developer zich geen zorgen te maken over het schrijven van SQL-queries of het omgaan met verbindingsproblemen met de database. Het stelt developers in staat om objecten rechtstreeks te koppelen aan hun bijbehorende databasegegevens, en vice versa.

- **Authenticatie:** Wie ben je?
- **Authorisatie:** Waar mag je bij?

Als gebruiker schiet jij als het ware een "submission" in.

**Salesforce API:** stel er is een nieuwe submissie met x bedrag en y banknummer, dan wordt het pakketje met deze informatie daarna op de achtergrond naar salesforce gestuurd.

**Tasks:** met een task runt in de achtergrond, die voor een backup/fallback zorgt. Stel dat salesforce het niet doet, dan kan je zelf instellen het ie het bijvoorbeeld nog x aantal probeert, maar dat het proces in ieder geval doorgaat. (dit werkt in de cloud)

**Brevo:** de emailpartner

**Docker:** draait op je windows. Docker kan andere kleinere operating systems draaien los van elkaar. De database wordt dan opgezet in een docker container. Wordpress kan ook in een docker container. Het is een soort "virtueel operating system".

**Linter:** een linter checkt je code tegen de standaard. Checkt op structuur, lege regels, indentation , etc.

Het geautomatiseerd runnen van processen en tools noem je een pipeline.

**Javascript VS Typescript:** Typescript is Javascript maar met allemaal types er over heen die je moet definiëren. Ze doen hetzelfde.

**Sonar:** onderdeel van de pipeline die je code controleert op fouten. Regels binnen code standaarden zoals waarschuwing tegen vreemde functies, security vulnerabilities.

Staging is de testversie van de website. Production staat live voor iedereen.

### Lijst met genoemde termen

- AWS / Google / Infra
- REST / Swagger docs
- SQL / Database / Migration SQL vs NoSQL
- Mikro ORM
- Docker / Pipelines 
- NPM / Linters
- Sonar
- HTTP request
- Authenticate /  Authorize
- Forms
- Submissions
- Tasks
- Salesforce
- Brevo

---

## Lokaal een project clonen met SSH

Om lokaal een project te clonen met een SSH key heb ik het volgende proces doorlopen.

### 1. GIT Installeren en configureren

**1. GIT installeren:**

GIT heb ik geïnstalleerd via de windows installer for git.

**2. GIT configureren:**

- [x] To open a command window, go to `Git Bash.vbs` from the Git folder of the Programs directory.
- [x] Enter the following command to configure your username

    `$ git config --global user.name "Anne van Dijk"`
- [x] Enter the following command to configure your email address

    `$ git config --global user.email "anne.van.dijk@usmedia.nl"`
- [x] Configure Git to handle line endings properly so that Bitbucket doesn't think files have changed when the actual content hasn't changed. We recommend this setting if you're collaborating on repositories with others who have different operating systems.

    For Windows: `$ git config --global core.autocrlf true`
    For Mac and Linux: `$ git config --global core.autocrlf input`


**Bron:** [Install and set up GIT](https://support.atlassian.com/bitbucket-cloud/docs/install-and-set-up-git/)

### 2. Set up personal SSH keys on Windows

**1. Download and install Git for Windows:**
- [x] Download and run the installer from https://gitforwindows.org/. The options at each step should be suitable. When you reach the step about choosing the SSH executable, ensure the bundled OpenSSH is selected.
- [x] Once the installation is complete, open `Git Bash` from the Start menu.
- [x] In the terminal, check that OpenSSH has been successfully installed by running the following command:

    `ssh -V`
  
    The output should show the installed version of OpenSSH.

**2. Start the SSH agent:**

- [x] From a git bash terminal, check if the SSH agent is running using the `ps` command. If the ssh-agent is already running, it should appear in the output, such as:

    `$ ps -a | grep ssh-agent`
    `tkelly      3291  0.0  0.0   6028   464 ?        Ss   07:29   0:00 ssh-agent`

- [x] To start the agent:

    `eval $(ssh-agent)`
  
You may need to add this command to your ~/.bashrc to ensure the agent starts when you open a Git Bash terminal. 

**3. Create an SSH key pair:**

- [x] Open a terminal and navigate to your home or user directory using cd, for example:

    `cd ~`

- [x] Generate a SSH key pair using ssh-keygen, such as:

    `ssh-keygen -t ed25519 -b 4096 -C "{username@emaildomain.com}" -f ~/.ssh/{ssh-key-name}`

  Where:

    `{username@emaildomain.com}` is the email address associated with the Bitbucket Cloud account, such as your work email account.

    `{ssh-key-name}` is the output filename for the keys. We recommend using a identifiable name such as `bitbucket_work`.
- When prompted to Enter passphrase, you can either provide a password or leave the password empty. If you input a password, you will be prompted for this password each time SSH is used, such as using Git command that contact Bitbucket Cloud (such as git push, git pull, and git fetch). Providing a password will prevent other users with access to the device from using your keys.
- Once complete, ssh-keygen will output two files:

    `{ssh-key-name}` — the private key.

    `{ssh-key-name}.pub` — the public key.

    These files will be stored in your user folder, such as `C:\Users\<username>\<ssh-key-name>`

**4. Add your key to the SSH agent:**

- [x] Run the following command, replacing the `{ssh-key-name}` with the name of the private key:

    `ssh-add ~/.ssh/{ssh-key-name}`
  
    To ensure the correct SSH key is used when connecting to Bitbucket, update or create your SSH configuration file (~/.ssh/config) with the following settings:

```
Host bitbucket.org
  AddKeysToAgent yes
  IdentityFile ~/.ssh/{ssh-key-name}
```
Where `{ssh-key-name}` is the name, bitbucket_work, of the private key file once it has been added to the ssh-agent.

**5. Provide Bitbucket Cloud with your public key:**

- [x] Select the Settings cog on the top navigation bar.
- [x] From the Settings dropdown menu, select Personal Bitbucket settings.
- [x] Under Security, select SSH keys.
- [x] Select Add key.
- [x] In the Add SSH key dialog, provide a Label to help you identify which key you are adding. For example, Work Laptop <Manufacturer> <Model>. A meaningful label will help you identify old or unwanted keys in the future.
- [x] Open the public SSH key file (public keys have the .pub file extension) in a text editor. The public key should be in the .ssh/ directory of your user (or home) directory. The contents will be similar to:

    `ssh-ed25529 LLoWYaPswHzVqQ7L7B07LzIJbntgmHqrE40t17nGXL71QX9IoFGKYoF5pJKUMvR+DZotTm user@example.com`
- [x] Copy the contents of the public key file and paste the key into the Key field of the Add SSH key dialog.
- [x] Select Add key.
If the key is added successfully, the dialog will close and the key will be listed on the SSH keys page.
If you receive the error That SSH key is invalid, check that you copied the entire contents of the public key (.pub file).

**6. Check that your SSH authentication works:**

- [x] To test that the SSH key was added successfully, open a terminal on your device (I used PowerShell) and run the following command:

    `ssh -T git@bitbucket.org`

If SSH can successfully connect with Bitbucket using your SSH keys, the command will produce output similar to:

`authenticated via ssh key.
You can use git to connect to Bitbucket. Shell access is disabled`

**Bron:** [Set up personal SSH keys on Windows](https://support.atlassian.com/bitbucket-cloud/docs/set-up-personal-ssh-keys-on-windows/)

### Cloning a project with SSH from Gitbucket.

Om een bestaand US project lokaal te clonen op mijn (nu nog) Windows laptop, ga ik in Gitbucket naar "projects", dan naar het desbetreffende project, dan naar de juiste repo, bijvoorbeeld "terre-des-hommes-website", en vervolgens naar "source". Hier staat rechtsboven de knop "clone", waar je vervolgens de SSH Key kan kopiëren. Dit kan er zo uit zien:

`git clone git@bitbucket.org:usmedia/project-naam.git`

Nadat deze gekopieërd te hebben heb ik VS code geopend, de terminal geopend, en de SSH Key geplakt in de terminal. Zorg ervoor dat je in de juiste map zit (bijvoorbeeld met `cd`) voordat je het project cloned. En zo heb ik nu een project lokaal op mijn laptop! 

**Bron:** [Configure SSH and 2-step verification](https://support.atlassian.com/bitbucket-cloud/docs/configure-ssh-and-two-step-verification/)

---
## 3 februari 2025

Vandaag was de eerste Stage dag bij US Media! Hier heb ik een onboarding gehad waar ik uitleg kreeg over alle algemene informatie wat betreft het bedrijf, de tools en de teams. Ook heb ik kennis gemaakt met verschillende developers en hebben we elkaars skills besproken.

Verder heb ik de US media wiki doorgespit en aantekeningen gemaakt van belangrijke dingen.

## 4 februari 2025

Dag 2 bij US. Ik ben de dag begonnen met het inventariseren van wat ik kon gaan doen, en had vervolgens om 9:15 een dailystandup met iedereen van US. Hierin besproken we wat we maandag hadden gedaan, wat we vandaag van plan waren te gaan doen en wat knelpunten waren.

Verder heb ik weer 3 kennismakingsgesprekken gehad en een workshop over US's [Formulieren API](#formulieren-api).

Tussen de meetings door heb ik de hele dag gewerkt aan het [lokaal clonen van een project via een SSH Key](#lokaal-een-project-clonen-met-ssh) en het installeren van alles wat hiervoor nodig is. Het clonen van een project is gelukt, alleen het lokaal live krijgen nog niet. Dat wordt dus het doel voor morgen!
