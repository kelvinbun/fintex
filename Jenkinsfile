pipeline {
  agent any
  triggers{
    pollSCM '* * * * *'
  }
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/kelvinbun/fintex.git', branch: 'master', credentialsId: 'Github'])

      }
    }
    stage('Deploy') {
      steps {
        echo '> Deploying the application ...'
        ansiblePlaybook(
           vaultCredentialsId: 'AnsibleVault',
           inventory: '/etc/ansible/hosts',
           playbook: '/etc/ansible/docker-playbook.yml'
           )
        }
     }
  }
}
