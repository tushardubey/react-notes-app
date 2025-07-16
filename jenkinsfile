pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-creds-id')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/tushardubey/react-notes-app.git'
            }
        }
    
    }
}
