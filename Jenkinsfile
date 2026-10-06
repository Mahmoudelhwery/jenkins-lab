pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Mahmoudelhwery/jenkins-lab.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // بناء صورة دوكر (تأكد من استبدال mahmoud/my-app باسم حسابك على Docker Hub واسم التطبيق)
                    sh 'docker build -t mahmoudelhwery/my-jenkins-app:latest .'
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    // إذا كنت تحتاج لتسجيل الدخول، يمكنك إضافة Credentials في جينكنز لاحقاً
                    // حالياً سنقوم برفع الصورة مباشرة إذا كانت الجلسة مسجلة
                    sh 'docker push mahmoudelhwery/my-jenkins-app:latest'
                }
            }
        }
    }
}
