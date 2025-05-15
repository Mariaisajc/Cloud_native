pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    bat 'docker build -t my-remix-app .'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests inside the Docker container
                    bat 'docker run --rm my-remix-app npm test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the Docker container to your server
                    bat 'docker run -d -p 3000:3000 my-remix-app'
                }
            }
        }
    }

    post {
        always {
            // Clean up Docker images and containers
            bat 'docker system prune -f'
        }
    }
}
