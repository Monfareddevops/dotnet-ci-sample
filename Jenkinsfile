pipeline {
    agent any

    tools {
            dotnetsdk 'dotnet9'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test --no-build --logger trx'
                junit '**/TestResults/*.trx'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/TestResults/*.trx', fingerprint: true
            }
        }
    }
}
