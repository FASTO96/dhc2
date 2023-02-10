

pipeline {


    agent {
        label "myage"
    }
environment
{
   DHC=credentials('dockerhub')
}




    stages {



        stage('git') {
            steps {
                checkout scm
            }
        }

        stage('build') {
            steps {
                sh "docker build -t sab22/wapp:1.1.$BUILD_NUMBER ."
            }
        }

       stage('login') {
         steps{

            sh 'echo $DHC_PSW | docker login -u $DHC_USR --password-stdin'
      }
   }

       stage('Deploy Image') {
         steps{

         sh 'docker push sab22/wapp:1.1.$BUILD_NUMBER'
    }
    }

    }

}
