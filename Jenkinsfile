pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/tushardubey/react-notes-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t notes_app:latest .'
            }
        }

    }
}
