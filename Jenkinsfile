pipeline {
    agent any
        stages {
            stage('Validate') {
                sh 'vagrant validate'
            }

            stage('List files') {
                sh 'ls'
            }
        }
}