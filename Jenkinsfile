pipeline {
  agent any
    
  tools {nodejs "nodejs"}
    
  stages {

    stage('Install dependencies') {
      steps {
        echo 'npm install'
      }
    }
     
    stage('Build') {
      steps {
         echo 'npm run build'
      }
    } 
    stage('Test') {
      steps {
        echo 'npm run test'
      }
    }
    
    
  }
}
