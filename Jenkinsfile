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

	stage('Docker Push') {
    steps {
        withCredentials([
            usernamePassword(
                credentialsId: 'dockerhub-credentials',
                usernameVariable: 'jenkinstest',
                passwordVariable: 'dckr_pat_7Cx_zQQHtj_wKeJems4KxDLR3QIN'
            )
        ]) {
            sh '''
                echo "$DOCKER_TOKEN" | docker login -u "$DOCKER_USER" --password-stdin
                docker tag myapp:${BUILD_NUMBER} $DOCKER_USER/jenkins-demo:${BUILD_NUMBER}
                docker push $DOCKER_USER/jenkins-demo:${BUILD_NUMBER}
                docker logout
            '''
        }
    }
}
       
       stage('Test') {
            steps {
                sh 'echo "Testing application"'
            }
        }
    }
}
