pipeline {
    agent { label 'master' }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/danielverissimo/project-web.git'
          }
        }
        stage('Build') {
            agent { docker 'maven:3.5-alpine' }
            steps {
                sh 'mvn clean package'
                
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
        stage('Deploy') {
          steps {
            input 'Do you approve the deployment?'
            
          }
        }
    }
}