pipeline {
  agent any

  stages {

    stage('Checkout') {
      steps {
        git 'https://github.com/Ryumiu/Demo-Serenity-Cucumber
      }
    }

    stage('Build & Test') {
      steps {
        // Usa la versión que tú tienes: apache-maven-3.9.11
        bat '"C:\\Maven\\apache-maven-3.9.11\\bin\\mvn.cmd" clean verify'
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
