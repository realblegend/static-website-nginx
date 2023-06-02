pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                // Checkout code from Git repository
                checkout scm

                // Build Docker image
                script {
                    docker.build('realblegend/my-static-website:1.0')
                }
            }
        }
        
        stage('Docker Image Push') {
            steps {
                sh 'docker push realblegend/my-static-website:1.0'
            }
        }
    }
}
