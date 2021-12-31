def branch = params.Branch
pipeline {
    agent any
    
    stages {
        stage('pull git code') {
            steps { 
                git branch: "$branch", credentialsId: '3f410fe8-ee67-4ae1-9f14-0d1f7737d33d', url: 'https://github.com/vijaymanikanta180/finalassessment.git'
            
            } 
        }
       
        stage('Build docker') {
            steps {
                // Run docker
                sh "docker build -t apache2:2.0 ."
                sh "docker run -itd -p 80:80 apache2:2.0"                
            }
        }
    }
}
