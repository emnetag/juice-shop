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
        sh 'npm install --production --unsafe-perm'
      }
    }
  }
}