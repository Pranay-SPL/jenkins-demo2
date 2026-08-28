pipeline {
    agent any

    parameters {
        choice(
            name: 'APP_NAME',
            choices: ['Banking Application', 'Shopping Application', 'Jenkins Demo'],
            description: 'Select Application'
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
            when {
                expression { 
                    params.ENVIRONMENT != 'Production'
                }
            }
            steps {
                echo "Deploying ${params.APP_NAME} to ${params.ENVIRONMENT}..."
                bat 'echo Deployment completed successfully'
            }
        }
    

    stage('Credentials Test') {
        steps {
            withCredentials([
                usernamePassword(
                    credentialsId: 'demo-credential',
                    usernameVariable: 'DEMO_USER',
                    passwordVariable: 'DEMO_PASSWORD'
                )
            ]) {
                bat '''
                    echo Username: %DEMO_USER%
                    echo Password: %DEMO_PASSWORD%
                '''
            }
        }
    }
    }

    post{
        always {
            echo 'Pipeline execution completed'
        }

        success {
            echo 'Pipeline completed Successfully!'
        }
        failure{
            echo 'Pipeline Failed!'
        }
    }

    


}