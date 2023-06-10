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
              bat 'sudo docker build -t new1 .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'sudo docker tag new1:latest hasee658/new1:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'sudo docker login -u hasee658 -p Nasha@786'
                bat 'sudo docker push hasee658/new1:latest'
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
