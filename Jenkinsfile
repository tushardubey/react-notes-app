pipeline {
    agent any

    environment {
        DOCKERHUB_CREDS = credentials('dockerhub-creds-id')
    }
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
        
        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds-id', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh """
                        echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                        docker push notes_app:latest
                    """
                }
            }
        }

    }
}
