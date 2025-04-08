pipeline{
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                     url: 'https://github.com/bash4bags/Elevate_Labs_Task_2_08_04_2025.git'
            }
        }

    stage('Build'){
        steps{
            echo 'Buiding the application...'

        }
    }

    stage('Test'){
        steps{
            echo 'Running tests..'

        }
    }

    stage('Deploy'){
        steps{
            echo 'Deploying the applictation...'
            sh 'docker build -t myapp .'
            sh 'docker run -d -p 80:80 myapp'
        }
    }
                }
    post{
        success{
            echo 'Pipeline completed successfully'
        }
        failure{
            echo 'Pipeline failed'
        }
    }
}