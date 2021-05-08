pipeline {
  agent any
    
  tools {nodejs "nodejs"}
    
  stages {

    stage('demo') {
      parallel{
        stage('demo-0'){
          steps{
          echo 'this is a demo'
          }
        }
        stage('demo-1'){
          stepa{
          echo 'this is demo-1'
          }
        }
      }
    }
      stage('hello'){
        parallel{
          stage('hello-1'){
            steps{
            echo 'hello-1'
            }
          }
        }
      }
    
          
      

    
    
    
    }
}
