pipeline {
    agent any
    environment {
        MICRO = 'academy'
       GIT_CRED = credentials('git') //username:password //secretkey
    }
    stages {
        stage('Build0') {
            steps {
                echo "${USER}"
              //  bat('set')
              //  sh "printenv | sort"
            }
        }
         stage('Build1') {
            steps {
                echo "${env.MICRO}"
              //  def password = ${GIT_CRED_PSW}
             //  sh 'echo %env.GIT_CRED%'
             // echo "${password}"
                echo "${env.GIT_CRED_USR}"
            }
        }
         stage('Build2') {
              when{
                  not {
                 branch "master"
                  }
             }
            steps {
                echo 'Building..'
            }
        }
         stage('Build3') {
             when {
                 not{
                branch "devops"
                 }
             }
            steps {
                 echo "${env.MICRO}"
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
/*node{
 def remote = [:]
  remote.name = 'oraclevm'
  remote.host = '152.67.160.182'
  remote.user = 'opc'
  remote.password = 'Muzammil073#'
  remote.allowAnyHosts = true
  stage('checkout') {
           checkout scm
  }  
 stage('step1'){
  sshPut remote: remote, from: 'syed00711.sh', into: '/home/opc'
 }
  stage('step2'){
     sshScript remote: remote, script: "syed00711.sh"
 }
  stage('step2'){
 sshCommand remote: remote, command: "pwd"
 }
  stage('step2'){
 sshRemove remote: remote, path: "/home/opc/syed00711.sh"
 }
}*/
