pipeline {
    agent any

    parameters {
        string(
            name: 'APP_NAME',
            defaultValue: 'Jenkins Demo',
            description: 'Enter Application Name'
        )

        choice(
            name: 'ENVIRONMENT',
            choices: ['Development', 'Testing', 'Production'],
            description: 'Select Environment'
        )

        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run Tests?'
        )
    }

    stages {

        stage('Application Details') {
            steps {
                echo "Application : ${params.APP_NAME}"
                echo "Environment : ${params.ENVIRONMENT}"
                echo "Run Tests   : ${params.RUN_TESTS}"
            }
        }

        stage('Jenkins Details') {
            steps {
                echo "Job Name     : ${env.JOB_NAME}"
                echo "Build Number : ${env.BUILD_NUMBER}"
                echo "Workspace    : ${env.WORKSPACE}"
            }
        }

        stage('Build') {
            steps {
                echo "Building ${params.APP_NAME}..."
                bat 'echo Build completed successfully'
            }
        }

        stage('Test') {
            when {
                expression {
                    params.RUN_TESTS == true
                }
            }

            steps {
                echo "Running tests..."
                bat 'echo Tests completed successfully'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${params.APP_NAME} to ${params.ENVIRONMENT}..."
                bat 'echo Deployment completed successfully'
            }
        }
    }
}