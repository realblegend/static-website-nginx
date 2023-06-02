pipeline {
    agent any

    stages {
        stage('Build and Push Docker Image') {
            steps {
                // Checkout code from Git repository
                checkout scm

                // Build Docker image
                script {
                    docker.build('realblegend/my-static-website:1.0')
                }
            }
        }
        
        stage('Run Docker Container') {
            steps {
                script {
                    docker.run("-d -p 8080:80 realblegend/my-static-website:1.0")
                }
            }
        }
    }
}
