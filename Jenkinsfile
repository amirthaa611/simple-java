pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/amirthaa611/simple-java.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t amirthaa06/simple-java-app:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f Deployment.yaml'
            }
        }
    }
}