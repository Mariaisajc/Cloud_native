pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                // Instala las dependencias con npm
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Ejecuta los tests
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                // Compila o construye el proyecto si aplica
                sh 'npm run build'
            }
        }

        stage('Run App (Optional)') {
            when {
                expression { return false } // Cambia a true si quieres ejecutar localmente
            }
            steps {
                // Ejecuta la app localmente (solo si es necesario y seguro)
                sh 'npm start'
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminado.'
        }
    }
}
