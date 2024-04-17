pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repository
                git 'https://github.com/mabdullahk3/ReactJsApp'
            }
        }
        stage('Dependency Installation') {
            steps {
                // Install dependencies for frontend
                bat 'npm install'
            }
        }
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                bat 'docker build -t REASCTJSAPP .'
            }
        }
        stage('Run Docker Image') {
            steps {
                // Run Docker container from the built image
                bat 'docker run -d -p 3000:80 REASCTJSAPP'
            }
        }
        stage('Push Docker Image') {
            steps {
                // Push Docker image to Docker Hub (assuming you have Docker Hub credentials configured)
                bat 'docker login -u mabdullah12 -p abdullahk03'
                bat 'docker tag REASCTJSAPP mabdullah12/REASCTJSAPP:latest'
                bat 'docker push mabdullah12/REASCTJSAPP:latest'
            }
        }
    }
}
