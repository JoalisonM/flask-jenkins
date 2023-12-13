pipeline {
    agent { docker { image '3.11.7-alpine3.19' } }
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