pipeline {
  agent any
    
  tools {nodejs "nodejs"}
    
  stages {

    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
     
    stage('Build') {
      steps {
         sh 'npm run build'
      }
    } 
    
    stage('Code Quality Check via SonarQube') {

      steps {
       script {
        def scannerHome = tool 'sonarqube';
           withSonarQubeEnv("sonarqube") {
           sh "${tool("sonarqube")}/bin/sonar-scanner \
           -Dsonar.projectKey=demo-2 \
           -Dsonar.sources=. \
           -Dsonar.host.url=http://172.17.0.1:9000 \
           -Dsonar.login=admin
	   -Dsonar.password=admin"

               }
           }
       }
   }


    
    stage('Package') {
      steps {
         sh 'ls -lrt'
         sh "pwd"
         sh "tar -zcf build.tar.gz build/"
      }
    }    
  }
}
