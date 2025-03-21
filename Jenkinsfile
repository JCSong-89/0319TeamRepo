pipeline {
    agent any

    environment {
        VENV_DIR = "${WORKSPACE}/venv"
    }

    stages {
        stage('Clone Repository') {
            steps {
                sh '''

                # 기존 디렉토리 삭제 (있다면)
                if [ -d "0319TeamRepo" ]; then
                    echo "🧹 기존 0319TeamRepo 디렉토리 삭제"
                    rm -rf 0319TeamRepo
                fi
                git clone 'https://github.com/JCSong-89/0319TeamRepo.git'
                '''

            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    cd 0319TeamRepo

                    pytest
                '''
            }
        }
    }

    post {
        always {
            sh '''
            echo 'Build finished.'
            '''
        }
    }
}
