pipeline { 
    agent any 
    stages {
        stage('Build local') { 
            steps { 
                sh 'vagrant validate'
            }
        }
         stage ('Build ansible') {
            steps {
                input 'Do you want to build thelinuxthing-ansible ?'
                build 'thelinuxthing-ansible'
            }
         }
    }
}
