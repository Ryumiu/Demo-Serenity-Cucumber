pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Ryumiu/Demo-Serenity-Cucumber.git', branch: 'master'
            }
        }

        stage('Build & Test') {
            steps {
                // Ejecutar Maven en Windows
                bat '"C:\\Maven\\apache-maven-3.9.11\\bin\\mvn.cmd" clean verify'
            }
        }

        stage('Report') {
            steps {
                // Publicar el reporte de Serenity (ajusta la ruta si es distinta)
                publishHTML([
                    reportName: 'Serenity Report',
                    reportDir: 'target/site/serenity',
                    reportFiles: 'index.html',
                    keepAll: true,
                    alwaysLinkToLastBuild: true,
                    allowMissing: true
                ])
            }
        }
    }
}
