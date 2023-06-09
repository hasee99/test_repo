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
              sh 'sudo docker build -t node_doc .'
            }
        }
         stage('Tag Image') {
           
            steps {
               sh 'sudo docker tag node_doc:latest syed0071/node_doc:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               sh 'sudo docker login -u syed0071 -p Syed0071#'
                sh 'sudo docker push syed0071/node_doc:latest'
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
