pipeline {
    agent any
    parameters {
      gitParameter branchFilter: 'origin/(.*)', defaultValue: 'version1', name: 'BRANCH', type: 'PT_BRANCH'
    } 
    stages {
        stage('pull git code') {
            steps { 
                git branch: "${params.BRANCH}", credentialsId: '3f410fe8-ee67-4ae1-9f14-0d1f7737d33d', url: 'https://github.com/vijaymanikanta180/projectfinal.git'
            
            } 
        }
       
        stage('Build docker') {
            steps {
                // Run docker
                sh "docker build -t apache2:1.0 ."
                sh "docker run -itd -p 81:80 apache2:1.0"                
            }
        }
    }
}
