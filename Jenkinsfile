pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Clone your forked repo
                git url: 'https://github.com/your-username/minfy-python-demo-av.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    docker build -t minfy-python-demo-av .
                }
            }
        }

        stage('Build Docker Tag') {
            steps {
                script {
                    // Tag the Docker 
                    docker tag minfy-python-demo-av avanishsah/minfy-python-demo-av:latest
                }
            }
        }

        stage('Push Docker') {
            steps {
                script {
                    // Push the Docker
                    docker push avanishsah/minfy-python-demo-av:latest                    
                }
            }
        }

        // Optional: Add test or deploy stages later
        stage('Test') {
            steps {
                echo 'Testing placeholder...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}