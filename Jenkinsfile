pipeline {
    agent any

    stages {

        stage('Docker Check') {
            steps {
                sh 'docker --version'
                sh 'docker ps'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Build started"'
                sh 'ls -la'
            }
        }rgrgrgrg

        stage('Test') {
            steps {
                sh 'echo "Testing application"'
            }
        }
    }
}
