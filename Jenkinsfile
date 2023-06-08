pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
         stage('Build Image') {
            steps {
              sh 'sudo docker build -t ubuntu_jenkins .'
            }
        }
         stage('Tag Image') {
           
            steps {
               sh 'sudo docker tag ubuntu_jenkins:latest syed0071/ubuntu:1.0.0'
            }
        }
         stage('Push Image') {
          
            steps {
               sh 'sudo docker login -u syed0071 -p Syed0071#'
                sh 'sudo docker push syed0071/ubuntu_jenkins:1.0.0'
            }
        }
    }
    post { 
        aborted { 
            echo 'ABORTED'
        }
         success { 
            echo 'SUCCESS'
        }
         failure { 
            echo 'FAILURE'
        }
        changed { 
            echo 'FAILURE'
        }
    }
    
}
