pipeline {
    agent { docker 'maven:3.5-alpine' }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/danielverissimo/project-web.git'
          }
        }
        stage('Build') {
            steps {
            		sh 'mvn clean package'            		    
            }
        }
        stage('Deploy') {
          steps {
            input 'Do you approve the deployment?'
            
          }
        }
    }
}