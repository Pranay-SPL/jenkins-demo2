pipeline {
    agent any

    stages {

        stage('Jenkins Details') {
            steps {
                bat """
                echo ==========================
                echo Jenkins Job Information
                echo ==========================

                echo Job Name      : %JOB_NAME%
                echo Build Number  : %BUILD_NUMBER%
                echo Build ID      : %BUILD_ID%
                echo Workspace     : %WORKSPACE%

                echo ==========================
                """
            }
        }

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