pipeline {
  agent any
  stages {
    stage('Powershell') {
      steps {
        catchError() {
          powershell(script: 'C:\\Users\\turboci\\Desktop\\Scripts\\test.ps1 1234', returnStatus: true)
        }

      }
    }
  }
}