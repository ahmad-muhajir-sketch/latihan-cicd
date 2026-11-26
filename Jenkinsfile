pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Test') {
            steps {
                sh '''
                grep -q "<html>" public/index.html
                grep -q "</html>" public/index.html
                grep -q "<title>" public/index.html
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp -r public/* /var/www/html/'
            }
        }
    }
}
