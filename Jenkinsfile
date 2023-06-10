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
              bat ' docker build -t new11 .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat ' docker tag new1:latest hasee658/new11:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat ' docker login -u hasee658 -p Nasha@786'
                bat ' docker push hasee658/new11:latest'
            }
        }
    }
    stage ('Run Image') {
            steps {
            bat 'docker run --name nh -p 7783:3070 -d  new11:latest'
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
