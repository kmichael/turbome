pipeline {
  agent any
  stages {
    stage('Install Client') {
      steps {
        powershell(returnStatus: true, returnStdout: true, script: 'C:\\Users\\turboci\\Desktop\\test-script.ps1')
      }
    }
    stage('Build Image') {
      parallel {
        stage('Build Image') {
          steps {
            bat(script: 'turbo build "C:\\Users\\turboci\\Desktop\\turbo.me" --overwrite 2>&1', returnStatus: true, label: 'Redirect 2>&1 ReturnStatus')
          }
        }
        stage('Return Nothing') {
          steps {
            bat(script: 'turbo build "C:\\Users\\turboci\\Desktop\\turbo.me" --overwrite', label: 'Return Nothing')
          }
        }
        stage('') {
          steps {
            bat(script: 'turbo build "C:\\Users\\turboci\\Desktop\\turbo.me" --overwrite 2>&1', label: 'Only Redirect & return nothing')
          }
        }
      }
    }
    stage('Test image') {
      steps {
        bat 'turbo check firefox-nightly'
      }
    }
  }
}