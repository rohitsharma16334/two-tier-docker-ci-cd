pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/rohitsharma16334/two-tier-docker-ci-cd.git'
            }
        }

        stage('Build Images') {
            steps {
                sh '''
                cd /mnt/wsl/Ubuntu/home/rohit/two-tier-ci-cd
                docker compose build
                '''
            }
        }

        stage('Deploy Containers') {
            steps {
                sh '''
                cd /mnt/wsl/Ubuntu/home/rohit/two-tier-ci-cd
                docker compose down || true
                docker compose up -d
                '''
            }
        }
    }
}

