pipeline {
    agent any

    stages {
        stage('Checkout repo') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                checkout scm
            }
        }
        stage('Restore dependancies') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build app') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run tests') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
