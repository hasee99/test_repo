pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
        stage('docker compose stop') {
          
            steps {
               sh 'docker-compose down'
            }
        }
           stage('docker compose start') {
          
            steps {
               sh 'docker-compose up -d'
            }
        }
        
         stage('push image') {
          
            steps {
               sh 'sudo docker login -u syed0071 -p Syed0071#'
                sh 'sudo docker push syed0071/compose_nginx_build:latest'
               // sh 'sudo docker push syed0071/compose_nginx_build:latest'
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
