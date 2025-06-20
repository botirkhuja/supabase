pipeline {
  agent {
    label 'jenkins-ubuntu-agent'
  }

  environment {
    SUPABASE_ENV_FILE = credentials('supabase-env-file');
  }

  stages {
    stage('source env file') {
      steps {
        script {
          sh '''
            set -a
            source $SUPABASE_ENV_FILE
            set +a
            echo "Environment variables loaded from .env file"
          '''
        }
      }
    }

    stage('echo environment variables') {
      steps {
        script {
          sh 'printenv'
        }
      }
    }
  }
}