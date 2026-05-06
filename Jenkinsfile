pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anmolkumar-prive/jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build step running...'
                echo 'python --v'
            }
        }

        stage('Test') {
            steps {
                echo 'Test step running...'
            }
        }
    }
}