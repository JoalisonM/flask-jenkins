pipeline {
    agent { docker { image 'python:3.10.12' } }
    stages {
        stage('build') {
            steps {
                sh 'python3 --version'
                // sh 'virtualenv venv'
                // sh '. venv/bin/activate'
                // sh 'pip3 install -r requirements.txt'
            }
        }
        stage('test') {
            steps {
                sh 'python test.py'
            }
        }
    }
}