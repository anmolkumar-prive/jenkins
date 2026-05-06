pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install --upgrade pip'
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh 'python3 app.py'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest -v'
            }
        }

    }

    post {
        always {
            echo 'Pipeline finished'
        }

        success {
            echo 'Build SUCCESS 🎉'
        }

        failure {
            echo 'Build FAILED ❌'
        }
    }
}