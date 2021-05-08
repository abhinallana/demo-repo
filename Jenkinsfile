pipeline {
  agent any
    
  tools {nodejs "nodejs"}
    
  stages {

    stage('demo') {
      parallel{
          stage('hello'){
            steps{
              echo 'hello world'
            }
          }
            stage('good morning'){
              steps{
                echo 'good morning'
              }
            }
      }
    }
     
    stage('Build') {
      parallel{
        stage('good eve'){
          steps{
            echo 'good eve'
          }
    } 
      }
 }
    stage('Test') {
      steps {
        echo 'test'
      }
      parallel{
        stage('good afternoon'){
          steps{
            echo 'good afternoon'
          }
        }
        stage('good nyt'){
          steps{
            echo 'good nyt'
          }
      }
   }
    }
}
}
