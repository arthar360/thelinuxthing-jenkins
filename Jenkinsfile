pipeline { 
    agent any 
    stages {
        stage('Build local') { 
            steps { 
                sh 'vagrant validate'
            }
        }
         stage ('Build ansible') {
            build {
                'thelinuxthing-jenkins'
            }
         }
    }
}
