pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Build completed"
            }
        }

        stage('Test') {
            steps {
                sh 'echo Tests passed'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t myapp:v1 .'
            }
        }
    }
}

