
pipeline {
    agent {
        label "myage"
    }
environment
{
    abc = "sab22/wapp:latest"
}
    stages {

        stage('git') {
            steps {
                checkout scm
            }
        }

        stage('build') {
            steps {
                sh "docker build -t $abc ."
            }
        }   
    }
    }



