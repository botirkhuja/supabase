pipeline {
  agent {
    label 'jenkins-ubuntu-agent'
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('echo environment variables') {
      steps {
        script {
          echo "env: ${env}"
        }
      }
    }
  }
}