pipeline {
  agent {
    label 'jenkins-ubuntu-agent'
  }

  environment {
    SUPABASE_ENV_FILE = credentials('supabase-env-file');
  }

  stages {
    stage('Deploy supabase stack') {
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
    // stage('read file') {
    //   steps {
    //     script {
    //       def envFile = readFile (SUPABASE_ENV_FILE)
    //       writeFile file: '.env', text: envFile
    //     }
    //   }
    // }
    // stage('source env file') {
    //   steps {
        
    //     // sh 'chmod 600 .env'
    //     // script {
    //       sh '''#!/bin/bash
    //         source .env
    //         echo "Environment variables loaded from .env file"
    //       '''
    //     // }
    //   }
    // }

    // stage('echo environment variables') {
    //   steps {
    //     script {
    //       sh 'printenv'
    //     }
    //   }
    // }
  }
}