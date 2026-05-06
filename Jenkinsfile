pipeline {
    agent any

    environment {
        IMAGE_NAME = "jenkins-python-app"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anmolkumar-prive/jenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Tests in Container') {
            steps {
                sh 'docker run --rm $IMAGE_NAME pytest -v'
            }
        }

        stage('Run App') {
            steps {
                sh 'docker run --rm $IMAGE_NAME'
            }
        }

    }

    post {
        success {
            echo 'PIPELINE SUCCESS 🎉'
        }

        failure {
            echo 'PIPELINE FAILED ❌'
        }
    }
}