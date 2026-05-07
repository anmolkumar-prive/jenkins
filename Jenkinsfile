pipeline {
    agent any

    parameters {

        choice(
            name: 'ENV',
            choices: ['dev', 'staging', 'prod'],
            description: 'Select environment'
        )

        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run tests before deployment'
        )
    }

    stages {

        stage('Build') {
            steps {
                echo "Building app..."
            }
        }

        stage('Test') {
            when {
                expression { params.RUN_TESTS == true }
            }

            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${params.ENV}"
            }
        }
    }
}