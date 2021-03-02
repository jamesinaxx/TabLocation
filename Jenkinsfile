pipeline {
  agent any
  stages {
    stage('Build TabLocation') {
      parallel {
        stage('Build TabLocation') {
          steps {
            bat 'mvn clean verify'
          }
        }

        stage('Check Java Version') {
          steps {
            bat 'java --version'
          }
        }

      }
    }

  }
}