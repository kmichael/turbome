pipeline {
  agent any
  stages {
    stage('Install Client') {
      steps {
        bat(script: 'powershell -File "C:\\Users\\turboci\\Desktop\\test-script.ps1"', returnStatus: true, returnStdout: true)
      }
    }
    stage('Build Image') {
      steps {
        bat(script: 'turbo build "C:\\Users\\turboci\\Desktop\\turbo.me" --overwrite', returnStatus: true, returnStdout: true)
      }
    }
    stage('Test image') {
      steps {
        bat 'turbo check firefox-nightly'
      }
    }
  }
}