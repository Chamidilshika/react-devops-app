pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Chamidilshika/react-devops-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t react-devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop react-container || true'
                sh 'docker rm react-container || true'
                sh 'docker run -d -p 3000:3000 --name react-container react-devops-app'
            }
        }
    }
}