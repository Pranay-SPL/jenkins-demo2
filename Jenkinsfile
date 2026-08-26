pipeline {
    agent any

    environment {
        APP_NAME = 'Jenkins Learning'
        APP_VERSION = '1.0'
        OWNER = 'Pranay'
    }

    stages {

        stage('Application Details') {
            steps {
                bat """
                echo ==========================
                echo App Name : %APP_NAME%
                echo Version : %APP_VERSION%
                echo Owner : %OWNER%
                echo ==========================

                """
            }
        }

        stage('Jenkins Details') {
            steps {
                bat"""
                echo ==========================
                echo Job     : %JOB_NAME%
                echo Build  : %BUILD_NUMBER%
                echo Workspace     : %WORKSPACE%
                echo ==========================
                """
            }
        }

        stage('Run Batch File') {
            steps {
                bat 'hello.bat'
            }
        }

        
        
    }
}