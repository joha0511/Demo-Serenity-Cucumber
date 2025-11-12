pipeline {
  agent any

  tools {
    maven 'Maven-3.8.6'   // ← usa el nombre que te sugiere Jenkins
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
