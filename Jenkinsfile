pipeline {
    agent {
        label 'default'
    }
        stages {
            stage('Validate') {
                steps{
                    sh 'vagrant validate'
                }
            }

            stage('List files') {
                steps{
                    sh 'ls'
                }
            }
        }
}