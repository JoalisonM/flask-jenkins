pipeline {
    agent { docker { image 'python:3.10.12' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
        // stage('test') {
        //     steps {
        //         sh 'python test.py'
        //     }
        // }
    }
}