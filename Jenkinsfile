pipeline {
    agent any

    stages {
        stage('Build and Push Docker Image') {
            steps {
                // Checkout code from Git repository
                checkout scm

                // Build Docker image
                script {
                    docker.build('realblegend/my-static-website:1.0').withDockerfile()
                }

                // Push Docker image
                script {
                    withDockerRegistry([credentialsId: 'docker-hub-credentials', url: 'https://registry.hub.docker.com']) {
                        docker.image('realblegend/my-static-website:1.0').push()
                    }
                }
            }
        }
    }
}
