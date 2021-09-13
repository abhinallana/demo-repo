pipeline {
  agent any
    
  tools {nodejs "nodejs"}
  parameters {
    extendedChoice( 
        defaultValue: 'One,Two,Three,Four', 
        description: 'please select the brand', 
        multiSelectDelimiter: ',', 
        name: 'environment', 
        quoteValue: false, 
        saveJSONParameterToFile: false, 
        type: 'PT_CHECKBOX', 
        value:'LTSB,BOS,HALIFAX,MBNA', 
        visibleItemCount: 4)
    }

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
        def scannerHome = tool 'sonar-scanner';
           withSonarQubeEnv("sonarqube-container") {
           sh "${tool("sonar-scanner")}/bin/sonar-scanner \
           -Dsonar.projectKey=demo-2 \
           -Dsonar.sources=. \
           -Dsonar.host.url=http://172.17.0.1:9000 \
           -Dsonar.login=admin \
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
