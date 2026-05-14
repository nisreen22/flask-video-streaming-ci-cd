pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install') {
            steps {
                sh 'pip3 install flask --break-system-packages || pip3 install flask'
            }
        }
        stage('Deploy') {
            steps {
                sh 'pkill -f app.py || true'
                sh 'nohup python3 app.py > log.txt 2>&1 &'
            }
        }
    }
}
