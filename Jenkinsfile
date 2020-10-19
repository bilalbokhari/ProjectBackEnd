pipeline {
  agent any
  environment {
    registryCredential = 'dockerhub'
  }
  stages {
    stage('Build application code') {
      steps {
        sh 'python app.py'
      }
    }
    stage('Build Docker image') {
      steps {
        sh 'docker build -t bilalbokharee/diceproject02 .'
      }
    }
    stage('Push Docker image to Dockerhub') {
        steps{
            script {
                docker.withRegistry( '', registryCredential ) {
                  sh 'docker push bilalbokharee/diceproject02:Backend'
                }
            }
        }
      }
    }
}
