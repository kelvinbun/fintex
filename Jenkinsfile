pipeline {
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/kelvinbun/fintex.git', branch: 'master', credentialsId: 'Github'])

      }
    }
    stage('Copy Source Docker') {
      steps{
        sshagent(['user']){
        export SSH_KEY="/root/.ssh"  
        sh 'scp -r /var/lib/jenkins/workspace/Docker-ansible root@192.168.20.178:/home/jenks'
        }
      }
    }
  }
}
