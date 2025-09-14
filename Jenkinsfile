pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/<your-username>/foodie_devops.git'
            }
        }

        stage('Install') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'pytest || true'
            }
        }

        stage('Deploy') {
            steps {
                sh 'gunicorn --workers 2 --bind 127.0.0.1:5000 app:app &'
            }
        }
    }
}
