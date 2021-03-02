pipeline {
  agent any
  stages {
    stage('Testing TabLocation') {
      parallel {
        stage('Test TabLocation') {
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

    stage('Build TabLocation') {
      steps {
        bat 'mvn clean install'
      }
    }

    stage('') {
      steps {
        archiveArtifacts(artifacts: 'target/TabLocation*.jar', onlyIfSuccessful: true, fingerprint: true)
      }
    }

  }
}