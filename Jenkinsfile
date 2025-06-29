pipeline {
    agent any

    stages {
        stage('Checkout repo') {
            when {
                branch 'main'
            }
            steps { 
                checkout scm
            }
        }
        stage('Restore dependancies') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build app') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run tests') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
