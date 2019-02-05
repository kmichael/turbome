pipeline {
  agent any
  stages {
    stage('Install Client') {
      steps {
        powershell(returnStatus: true, returnStdout: true, script: 'C:\\Users\\turboci\\Desktop\\test-script.ps1')
        powershell(script: 'C:\\Users\\turboci\\Desktop\\test-script2.ps1', returnStatus: true, returnStdout: true, label: 'Write Output')
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