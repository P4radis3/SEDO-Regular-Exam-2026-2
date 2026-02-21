pipeline {
    agent any
    stages {
        stage('Restore Dependencies') {
            when {
                branch: "main"
            }
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            when {
                branch: "main"
            }
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            when {
                branch: "main"
            }
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}