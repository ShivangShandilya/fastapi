pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository from GitHub
                git 'https://github.com/ShivangShandilya/fastapi.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                // Build Docker image with new changes
                sh 'docker build -t fastapi:latest .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                // Login to Docker Hub using auth token
                sh 'docker login -u shivangshandilya -p dckr_pat_rE2MVUvjWMo0iHctgDNs8d_yQwQ'
            }
        }
        stage('Push Docker Image') {
            steps {
                // Push Docker image with a new tag to Docker Hub
                sh 'docker tag fastapi:latest shivangshandilya/napptive_hackathon:new-tag'
                sh 'docker push shivangshandilya/napptive_hackathon:new-tag'
            }
        }
    }
}
