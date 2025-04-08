pipeline {
    agent any
    tools {
        dockerTool 'docker'  // Use the managed Docker installation named 'docker'
    }
    environment {
        DOCKER_IMAGE = 'myapp'
        DOCKER_PORT = '80'
    }
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
                script {
                    // Build Docker image
                    sh "docker build -t ${env.DOCKER_IMAGE} ."
                    
                    // Stop and remove any existing container
                    sh "docker stop ${env.DOCKER_IMAGE} || true"
                    sh "docker rm ${env.DOCKER_IMAGE} || true"
                    
                    // Run new container
                    sh "docker run -d -p ${env.DOCKER_PORT}:${env.DOCKER_PORT} --name ${env.DOCKER_IMAGE} ${env.DOCKER_IMAGE}"
                }
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