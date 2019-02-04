pipeline {
  agent any
  stages {
    stage('Install Client') {
      steps {
        powershell(script: 'Write-Host "Test script starts" Write-Host "install turbo client" $ClientEditions = Get-ChildItem "\\\\s13\\Release\\Client" $installerPath = $ClientEditions[$ClientEditions.Length - 1].FullName+"\\Turbo-Plugin.exe" Write-Host "Installing client from $installerPath" & $installerPath --silent Write-Host "Installed Client with exit code $LASTEXITCODE" Write-Host "Turbo version:" & turbo version', returnStatus: true, returnStdout: true)
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