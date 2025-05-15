pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Run App (Optional)') {
            when {
                expression { return false } // Cambia a true si quieres ejecutar localmente
            }
            steps {
                bat 'npm start'
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminado.'
        }
    }
}
