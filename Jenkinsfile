pipeline {
    agent { docker { image 'python:3.7.2' } }
    stages {
        stage('upgrade_pip') {
            steps {
                script {
                    sh 'pip install --upgrade pip --user'
                }
            }
        }
        stage('build') {
            steps {
                script {
                    sh 'python -m venv venv'
                    sh '. venv/bin/activate'
                    sh 'pip install Flask --user'
                }
            }
        }
        stage('test') {
            steps {
                sh 'python3 test.py'
            }
        }
    }
}