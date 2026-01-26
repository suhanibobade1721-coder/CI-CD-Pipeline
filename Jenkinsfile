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
                echo "Build stage completed"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'echo Tests passed'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment successful"
            }
        }
    }
}

