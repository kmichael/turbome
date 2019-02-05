pipeline {
  agent any
  stages {
    stage('Install Client') {
      steps {
        powershell(returnStatus: true, returnStdout: true, script: 'C:\\Users\\turboci\\Desktop\\test-script.ps1')
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
