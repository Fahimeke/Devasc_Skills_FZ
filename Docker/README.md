# Devasc_Skills_FZ



Taaknaam: Docker

Taakvoorbereiding:
Voordat ik aan deze taak begon, zorgde ik ervoor dat:

Docker geïnstalleerd was op mijn machine.
Ik mezelf vertrouwd maakte met het verstrekte Ansible-playbook en de beoogde configuratie.
Ik een standaard HTML-pagina maakte die overeenkwam met de gespecificeerde elementen.
Taakimplementatie:

Interpretatie van Ansible-playbook:

Ik heb het Ansible-playbook begrepen en de instructies vertaald naar een Dockerfile.
Dockerfile:

Ik heb een Dockerfile opgesteld om de gewenste configuratie binnen een Docker-image te encapsuleren.
Dockerfile
Copy code
FROM ubuntu:latest

RUN apt-get update && apt-get install -y apache2 && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

COPY files/index.html /var/www/html/index.html

EXPOSE 8088

CMD ["apache2ctl", "-D", "FOREGROUND"]
Bash-script:

Ik heb een bash-script geschreven om het bouwen van het Docker-image en het starten van de Apache-container te automatiseren.
bash
Copy code
#!/bin/bash

# Bouw Docker-image
docker build -t apache-microservice .

# Start Apache-container
docker run -d -p 8088:80 --name apache-container apache-microservice
Aangepaste startpagina:

Ik heb een HTML-bestand met de naam index.html gemaakt met de gevraagde elementen.
html
Copy code
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevNet Associate Skills Test: Jouw Naam</title>
</head>
<body>
    <header>
        <h1>DevNet Associate Skills Test</h1>
        <p>Gemaakt door: Jouw Naam</p>
        <p>Datum: Huidige datum en tijd</p>
    </header>
</body>
</html>
Uitvoering van de taak:

Ik heb het bash-script uitgevoerd om het Docker-image te bouwen en de Apache-container te starten.
Probleemoplossing:

Ik heb ervoor gezorgd dat Docker correct was geïnstalleerd en operationeel was.
Grondige controles uitgevoerd op syntaxfouten in de Dockerfile en HTML.
Zorgvuldig gecontroleerd of het verstrekte playbook nauwkeurig was geïnterpreteerd in de Dockerfile.
Verificatie van de taak:

Verificatie Docker-image:

Ik heb docker images uitgevoerd om te bevestigen dat het "apache-microservice" image met succes is gemaakt.
Verificatie Docker-container:

Met docker ps heb ik gecontroleerd of de Apache-container actief was.
Toegang tot de Apache-startpagina:

Ik opende een webbrowser en ging naar http://localhost:8088 om te bevestigen dat de aangepaste startpagina met de gespecificeerde elementen correct werd weergegeven.
Screenshots:

Ik heb screenshots gemaakt op cruciale momenten, wat visueel bewijs levert van het maken van het Docker-image, het actief zijn van de container en het succesvol renderen van de Apache-startpagina.

![image](https://github.com/Fahimeke/Devasc_Skills_FZ/assets/91051172/5b8afa1c-490f-4c07-a93f-f49b9f433936)
![image](https://github.com/Fahimeke/Devasc_Skills_FZ/assets/91051172/0cca3359-a0f5-4fec-bec5-f0f0b1a4a66e)

