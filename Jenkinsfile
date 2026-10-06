pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t mahmoudelhwery/my-jenkins-app:latest .'
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    sh 'docker push mahmoudelhwery/my-jenkins-app:latest'
                }
            }
        }
    }
}
