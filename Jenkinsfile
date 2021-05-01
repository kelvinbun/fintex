pipeline {
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/kelvinbun/docker-test.git', branch: 'master', credentialsId: 'Github'])

      }
    }
    stage('Copy Source Docker') {
      steps{
        sshagent(credentials: ['deploy_user']){
//          sh "ssh -o StrictHostKeyChecking=no root@192.168.20.178"
//            sh "scp -r docker-compose-prod.yml ubuntu@remoteip:."
//        sh 'ssh -o StrictHostKeyChecking=no root@192.168.20.178 uptime'
        sh 'scp -r /var/lib/jenkins/workspace/Docker-ansible/ -o StrictHostKeyChecking=no root@192.168.20.178:/home/jenks'
        }
      }
    }
  }
}
