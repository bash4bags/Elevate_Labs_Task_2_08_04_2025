pipeline{
    agent any

    stages {
        stage('Checkout'){
            steps{
                echo 'fetching code form github...'
                git 'https://github.com/bash4bags/Elevate_Labs_Task_2_08_04_2025'
            }
        }

    stage('Build'){
        steps{
            echo 'Buiding the application...'
            sh 'npm install'
        }
    }

    stage('Test'){
        steps{
            echo 'Running tests..'
            sh 'npm test'
        }
    }

    stage('Deploy'){
        steps{
            echo 'Deploying the applictation...'
            sh 'docker build -t myapp .'
            sh 'docker run -d -p 80:80 myapp'
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
}