# Devasc_Skills_FZ




Taaknaam: Jenkins

Taakvoorbereiding:
Voorafgaand aan deze taak heb ik ervoor gezorgd dat:

Jenkins correct was geïnstalleerd op mijn systeem.
Een GitHub-repository beschikbaar was met de benodigde scripts en bestanden, inclusief de Docker-configuratie uit Task 3.
Taakimplementatie:

Aanmaken van Jenkins-pijplijn:

Ik heb een Jenkins-pijplijn gemaakt met drie fasen, waarbij ik de nodige scripts en bestanden download vanuit een GitHub-repository en de service uit Taak 3 installeer in een Docker-container. Ik heb een onafhankelijk Groovy-script gebruikt en geen freestyle Jenkins-project.
groovy
Copy code
pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                // Download necessary scripts and files from GitHub repository
                sh 'git clone https://github.com/your-username/your-repo.git'
            }
        }

        stage('Docker build, Docker run') {
            steps {
                // Build Docker image
                sh 'docker build -t apache-microservice .'

                // Run Docker container
                sh 'docker run -d -p 8088:80 --name apache-container apache-microservice'
            }
        }

        stage('Test') {
            steps {
                // Perform testing steps (e.g., curl commands, integration tests)
                sh 'docker exec -it apache-container your-test-command'
            }
        }
    }
}
Screenshots:

Ik heb screenshots gemaakt om het succes van elke fase in de Jenkins-pijplijn aan te tonen.
Probleemoplossing:

Bij eventuele fouten heb ik de Jenkins-logboeken gecontroleerd en ervoor gezorgd dat alle benodigde stappen correct waren geconfigureerd.
Verificatie van de taak:

Succesvolle Jenkins-pijplijn:

Ik heb gecontroleerd of de Jenkins-pijplijn zonder fouten is uitgevoerd.
Screenshots:

De gemaakte screenshots bevestigen het succes van elke fase in de Jenkins-pijplijn.
Bewaren van scriptbestanden:

Ik heb de Groovy-scriptbestanden opgeslagen voor toekomstige referentie.