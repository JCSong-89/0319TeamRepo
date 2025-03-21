pipeline {
    agent any

    environment {
        VENV_DIR = "${WORKSPACE}/venv"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git clone 'https://github.com/JCSong-89/0319TeamRepo.git'
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    pytest
                '''
            }
        }
    }

    post {
        always {
            echo 'Build finished.'
        }
    }
}
