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
        ansiblePlaybook credentialsId: 'jenkins-agent-ansible-generated-key',
            disableHostKeyChecking: true,
            // installation: 'ansible',
            // become: true,
            // sudoUser: 'botir',
            // becomeUser: 'botir',
            colorized: true,
            // forks: 2,
            // startAtTask: '004',
            // tags: DEPLOYING_STACK,
            // vaultCredentialsId: 'external_hdd_uuid',
            // vaultTmpPath: '',
            inventory: 'inventory.yaml',
            playbook: 'playbook.yaml'
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