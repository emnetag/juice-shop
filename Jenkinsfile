pipeline {

  agent {
    docker {
      image 'node:9'
      args '-u root:root'
    }
  }
  
  stages {
    stage('Build') {
      steps {
        sh 'ls -al'
        sh 'sudo chown -R $USER:$(id -gn $USER) /.config'
        sh 'npm install --production --unsafe-perm'
      }
    }
  }
}