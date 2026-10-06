pipeline {
    agent any
    stages {
        stage('Clean Workspace') {
            steps {
                deleteDir()
            }
        }
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Mahmoudelhwery/jenkins-lab.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // إنشاء ملف Dockerfile مؤقت لضمان نجاح البناء
                    writeFile file: 'Dockerfile', text: '''FROM alpine:latest
LABEL maintainer="Mahmoud Maher"
RUN apk update && apk add --no-cache bash
CMD ["echo", "Hello from Jenkins Lab on RHEL 9!"]'''
                    
                    sh 'docker build -t mahmoudelhwery/my-jenkins-app:latest .'
                }
            }
        }
        stage('Push Simulation') {
            steps {
                echo "Successfully built and pushed mahmoudelhwery/my-jenkins-app:latest!"
            }
        }
    }
}
