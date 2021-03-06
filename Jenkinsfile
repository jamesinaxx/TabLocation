pipeline {
  agent any
  stages {
    stage('Testing TabLocation') {
      parallel {
        stage('Test TabLocation') {
          steps {
            sh '''#!/bin/bash
mvn clean verify'''
          }
        }

        stage('Check Java Version') {
          steps {
            sh '''#!/bin/bash
java --version'''
          }
        }

      }
    }

    stage('Build TabLocation') {
      steps {
        sh '''#!/bin/bash
mvn clean install'''
      }
    }

    stage('Archive Artifacts') {
      steps {
        archiveArtifacts(artifacts: 'target/TabLocation*.jar', onlyIfSuccessful: true, fingerprint: true)
      }
    }

  }
}