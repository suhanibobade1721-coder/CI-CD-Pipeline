pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/suhanibobade1721-coder/CI-CD-Pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t suhanibobade/myapp:v1 .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-pass', variable: 'DOCKER_PASS')]) {
                    bat 'echo %DOCKER_PASS% | docker login -u suhanibobade --password-stdin'
                }
            }
        }

        stage('Push Image') {
            steps {
                bat 'docker push suhanibobade/myapp:v1'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8081:80 suhanibobade/myapp:v1'
            }
        }
    }
}

