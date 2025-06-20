pipeline {
  agent {
    label 'jenkins-ubuntu-agent'
  }

  stages {
    stage('echo environment variables') {
      steps {
        script {
          sh `printenv`
        }
      }
    }
  }
}