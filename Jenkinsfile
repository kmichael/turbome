pipeline {
  agent any
  stages {
    stage('Powershell') {
      steps {
        powershell(script: '"C:\\Users\\turboci\\Desktop\\Scripts\\runScriptRemote-script.ps1" "C:\\Users\\turboci\\Desktop\\Scripts\\turboBuild-script.ps1" "CI-W732" "firefox\\base\\turbo.me","--overwrite"', returnStatus: true)
      }
    }
  }
}