pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Yazhiniyazhu/KUBERNETES--LAB.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t set11-app:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl rollout restart deployment/set11-app'
                bat 'kubectl rollout status deployment/set11-app'
            }
        }
    }
}
