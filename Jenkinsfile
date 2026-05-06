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

        stage('Run Tests') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    pytest -v
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Docker Container') {
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