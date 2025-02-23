pipeline {
    agent any

    environment {
        DOTNET_VERSION = '8.0' // Adjust as needed
    }

    stages {
        stage('Checkout') {
            
            steps {
                checkout scm
            }
        }
        stage('Restore Dependencies') {
         
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build Application') {
           
            steps {
                bat 'dotnet build --configuration Release'
            }
        }
        stage('Run Tests') {
           
            steps {
                bat 'dotnet test'
            }
        }
    }

    post {
        success {
            echo "Build and tests completed successfully."
        }
        failure {
            echo "Build or tests failed. Please review the logs."
        }
    }
}
