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
                    docker.build("minfy-python-app:latest")
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