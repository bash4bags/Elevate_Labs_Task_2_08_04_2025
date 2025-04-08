pipeline {
    agent any

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
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                script {
                    // Ensure Docker is available on the agent
                    sh "docker build -t ${env.DOCKER_IMAGE} ."
                    sh "docker stop ${env.DOCKER_IMAGE} || true"
                    sh "docker rm ${env.DOCKER_IMAGE} || true"
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