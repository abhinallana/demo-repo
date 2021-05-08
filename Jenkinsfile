pipeline {
  agent any
    
  tools {nodejs "nodejs"}
    
  stages {

    stage('demo') {
      parallel{
        stage('demo-0'){
          echo 'this is a demo'
        }
        stage('demo-1'){
          echo 'this is demo-1'
        }
      }
    }
      stage('hello'){
        parallel{
          stage('hello-1'){
            echo 'hello-1'
          }
        }
      }
    
          
      

    
    
    
    }
}
