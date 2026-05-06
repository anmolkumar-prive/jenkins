pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/anmolkumar-prive/jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build step running...'
            }
        }

        stage('Test') {
            steps {
                echo 'Test step running...'
            }
        }
    }
}