
pipeline {

  environment {
    dockerimagename = "sab22/wapp"
    dockerImage = ""
  }

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/FASTO96/dhc2.git'
      }
    }

    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build dockerimagename
        }
      }
    }

    stage('Pushing Image') {

      steps{
        script {
          docker.withRegistry( 'https://registry.hub.docker.com', dockerhub ) {
            dockerImage.push("latest")
          }
        }
      }
    }



  }

}
