pipeline {
    agent { docker { image 'python:3.7.2' } }
    stages {
        stage('build') {
            steps {
                sh 'python -m venv venv'
                sh '. venv/bin/activate && pip install Flask && pip install xmlrunner'
            }
        }
        stage('test') {
            steps {
                sh '. venv/bin/activate && python3 test.py'
            }
        }
    }
}