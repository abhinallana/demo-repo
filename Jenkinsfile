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
          steps{
          echo 'this is demo-1'
          }
        }
        stage('demo-2'){
          steps{
            echo 'this is demo-2'
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
          stage('hello-2'){
            steps{
              echo 'this is hello-2'
            }
          }
        }
      }
    stage('final'){
      parallel{
        stage('final-1'){
          steps{
            echo 'this is final-1'
          }
        }
      }
    }
    
          
      

    
    
    
    }
}
