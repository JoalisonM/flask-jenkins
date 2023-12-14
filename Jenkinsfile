pipeline {
    agent { docker { image 'python:3.7.2' } }
    stages {
        stage('build') {
            steps {
                sh 'python -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r --user requirements.txt'
            }
        }
        stage('test') {
            steps {
                sh 'python3 test.py'
            }
        }
    }
}