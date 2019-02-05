pipeline {
  agent any
  stages {
    stage('Trigger remote build') {
      steps {
        powershell(returnStatus: true, script: 'C:\\Users\\turboci\\Desktop\\host-script.ps1')
      }
    }
  }
}