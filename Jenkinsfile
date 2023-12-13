pipeline {
    agent { docker { image 'python:3.10.12' } }
    stages {
        stage('build') {
            steps {
                sh 'pip install virtualenv && virtualenv venv && . venv/bin/activate && pip install -r requirements.txt'
            }
        }
        stage('test') {
            steps {
                sh 'python test.py'
            }
        }
    }
}