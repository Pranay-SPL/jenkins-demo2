pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'hello.bat'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo Tests completed successfully'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                bat 'echo Deployment completed successfully'
            }
        }

    }
}