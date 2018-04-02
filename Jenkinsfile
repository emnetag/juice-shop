pipeline {
  agent {
    docker {
      image 'node:9-alpine'
      args '-p 3030:3030 -u root:root'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
  }
}