pipeline {
    agent any

    stages {

        stage('Docker Check') {
            steps {
                sh 'docker --version'
                sh 'docker ps'
            }
        }

	stage('Docker Build') {
            steps {
                sh 'docker build -t myapp:${BUILD_NUMBER} .'
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
