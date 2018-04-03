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
        sh 'npm install'
      }
    }
    stage('Veracode Scan') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'VERACODE_CREDS', passwordVariable: 'VERACODE_PASS', usernameVariable: 'VERACODE_ID')]) {
          veracode applicationName: "juice-shop",
                  canFailJob: true,
                  createProfile: true,
                  criticality: 'Medium',
                  debug: true,
                  fileNamePattern: '',
                  replacementPattern: '',
                  sandboxName: '',
                  scanExcludesPattern: '', 
                  scanIncludesPattern: '',
                  scanName: '$projectname-$buildnumber',
                  teams: '',
                  timeout: 60,
                  uploadExcludesPattern: 'test/**, screenshots/**',
                  uploadIncludesPattern: '',
                  useIDkey: true,
                  vid: env.VERACODE_ID,
                  vkey: env.VERACODE_PASS
        }
      }
    }
  }
}