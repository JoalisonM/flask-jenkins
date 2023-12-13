pipeline {
    agent { docker { image 'python:3.10.12' } }
    stages {
        stage('build') {
            steps {
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