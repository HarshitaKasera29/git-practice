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
                sh 'echo "Build started"'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Testing application"'
            }
        }
    }
}
