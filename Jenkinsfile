pipeline {
    agent {
        label 'myage'
    }
    environment{
        dockimage="sab22/wapp"
        dockb =""
        
    }
    
    stages {
        stage('git') {
            steps {
                git 'https://github.com/FASTO96/dhc2.git'
            }
        }
        
    stages {
        stage('build') {
            steps {
                dockb = docker.build dockimage
            }
        }
        
    stages {
        stage('push') {
            steps {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                    dockb.push("latest")
                }
            }
        }
    
        
        
        
    }
}
