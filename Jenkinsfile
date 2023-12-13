pipeline {
    agent { docker { image 'python:3.10.12' } }
    stages {
        stage('build') {
            steps {
                sh 'apt install python3-pip'
                sh 'pip3 --version'
                sh 'pip3 install flask'
            }
        }
        stage('test') {
            steps {
                sh 'python test.py'
            }
        }
    }
}