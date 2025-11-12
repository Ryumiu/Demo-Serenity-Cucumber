pipeline {
  agent any

  stages {

    stage('Checkout') {
      steps {
        git 'https://github.com/Laura4lilavati/Demo-Serenity-Cucumber.git'
      }
    }

    stage('Build & Test') {
      steps {
        // Ruta COMPLETA a Maven (fíjate en las dobles barras \\ y las comillas)
        bat '"C:\\Maven\\apache-maven-3.8.6\\bin\\mvn.cmd" clean verify'
      }
    }

    stage('Report') {
      steps {
        publishHTML(
          target: [
            reportDir: 'target/site/serenity',
            reportFiles: 'index.html',
            reportName: 'Serenity Report',
            allowMissing: false,
            keepAll: true,
            alwaysLinkToLastBuild: true
          ]
        )
      }
    }
  }
}
