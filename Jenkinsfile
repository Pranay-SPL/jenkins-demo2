pipeline {
    agent any

    parametres {
        string(
            name: 'APP_NAME',
            defaultValue: 'Jenkins Demo',
            description: 'Enter Application Name'
        )
        choice(
            name : 'ENVIRONMENT',
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

        stage('Display Parameters') {
            steps {
                echo "Application : ${params.APP_NAME}"
                echo "Environment : ${params.ENVIRONMENT}"
                echo "Run Tests   : ${param.RUN_TESTS}"
            }
        }

        stage('Build') {
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
