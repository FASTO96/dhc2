
pipeline {
    agent {
        label "myage"
    }

    stages {

        stage('git') {
            steps {
                checkout scm
            }
        }

        stage('build') {
            steps {
                sh "docker build -t sab22/wapp:latest ."
            }
        }   
    }
    }



