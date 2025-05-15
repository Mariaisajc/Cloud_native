pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    echo 'docker build -t my-remix-app .'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests inside the Docker container
                    echo 'docker run --rm my-remix-app npm test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the Docker container to your server
                    echo 'docker run -d -p 3000:3000 my-remix-app'
                }
            }
        }
    }

    post {
        always {
            // Clean up Docker images and containers
            echo 'docker system prune -f'
        }
    }
}
