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
        // script {
          sh '''
            cat $SUPABASE_ENV_FILE
            source $SUPABASE_ENV_FILE
            echo "Environment variables loaded from .env file"
          '''
        // }
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