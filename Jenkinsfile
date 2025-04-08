pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/bash4bags/Elevate_Labs_Task_2_08_04_2025.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add any build commands here if needed
                // Example for Node.js: sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests..'
                // Add test commands here if needed
                // Example: sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}