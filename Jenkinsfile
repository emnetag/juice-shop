pipeline {
  agent {
    docker {
      image 'node:9'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install --production --unsafe-perm'
      }
    }
  }
}