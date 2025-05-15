pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                dir('10-net9-remix-pg-env') {
                    bat 'npm install'
                }
            }
        }

        stage('Test') {
            steps {
                dir('10-net9-remix-pg-env') {
                    bat 'npm test'
                }
            }
        }

        stage('Build') {
            steps {
                dir('10-net9-remix-pg-env') {
                    bat 'npm run build'
                }
            }
        }

        stage('Run App (Optional)') {
            when {
                expression { return false }
            }
            steps {
                dir('10-net9-remix-pg-env') {
                    bat 'npm start'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminado.'
        }
    }
}
