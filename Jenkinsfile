pipeline {
    agent { docker { image 'python:3.10.12' } }
    stages {
        stage('build') {
            steps {
                sh 'apk add py-pip'
                sh 'apk add python-dev libffi-dev openssl-dev gcc libc-dev make'
                sh 'virtualenv venv'
                sh 'source venv/bin/activate'
                sh 'pip install flask'
            }
        }
        stage('test') {
            steps {
                sh 'python test.py'
            }
        }
    }
}