pipeline {
  agent any

  tools {
    maven 'Maven3'   // ← el mismo nombre que pusiste en Jenkins
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/joha0511/Demo-Serenity-Cucumber.git'
      }
    }

    stage('Build & Test') {
      steps {
        bat 'mvn clean verify'
      }
    }

    stage('Report') {
      steps {
        publishHTML(target: [
          reportDir: 'target/site/serenity',
          reportFiles: 'index.html',
          reportName: 'Serenity Report',
          keepAll: true,
          alwaysLinkToLastBuild: true,
          allowMissing: false
        ])
      }
    }
  }
}
