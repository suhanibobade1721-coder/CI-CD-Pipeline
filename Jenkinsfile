pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/suhanibobade1712/cicd-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t suhanibobade/myapp:v1 .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-pass', variable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u suhanibobade --password-stdin'
                }
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push suhanibobade/myapp:v1'
            }
        }
    }
}

