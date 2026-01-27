pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/suhanibobade1721-coder/CI-CD-Pipeline.git'
            }
        }

        stage('Build Docker Image v2') {
            steps {
                sh 'docker build -t suhanibobade/myapp:v2 .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-pass', variable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u suhanibobade --password-stdin'
                }
            }
        }

        stage('Push Image v2') {
            steps {
                sh 'docker push suhanibobade/myapp:v2'
            }
        }
    }
}




