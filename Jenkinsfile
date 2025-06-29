pipeline {
    agent any

    stages {
		stage ('Checkout repo') {
			steps { 
				checkout scm
			}
		}
        stage('Restore dependancies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build app') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Tests run') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}