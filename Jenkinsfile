pipeline {
  agent {
    docker {
      image 'mcr.microsoft.com/dotnet/sdk:6.0'
    }
  }
  stages {
    stage('Restore') {
      steps {
        sh 'dotnet restore'
      }
    }
    stage('Build') {
      steps {
        sh 'dotnet build'
      }
    }
    stage('Test') {
      steps {
        sh 'dotnet test'
      }
    }
  }
}
