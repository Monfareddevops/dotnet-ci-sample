pipeline {
    agent any

    tools {
        dotnet 'dotnet9'
    }

    stages {
        stage('Info') {
            steps {
                sh 'dotnet --info'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build'
            }
        }
    }
}
