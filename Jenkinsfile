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
	//sh 'npm install'
	echo "step-1"
      }
    }
     
    stage('Build') {
       steps { 
         //sh 'npm run build'
	  echo " step-2"
      }
    } 
    
    stage('Code Quality Check via SonarQube') {

      steps {
       script {
        def scannerHome = tool 'sonar-scanner';
           withSonarQubeEnv("sonarqube-container") {
           sh "${tool("sonar-scanner")}/bin/sonar-scanner \
           -Dsonar.projectKey=demo \
           -Dsonar.sources=. \
           -Dsonar.host.url=http://172.17.0.3:9000 \
           -Dsonar.login=admin \
	   -Dsonar.password=admin"
		   if(env.branch.contains(release)){
			   echo "release-1"
		   }else{
			   echo "new branch"
               }
           }
       }
   }


    
    stage('Package') {
      steps {
         //sh 'ls -lrt'
         //sh "pwd"
         //sh "tar -zcf build.tar.gz build/"
	 echo "success"
      }
    }    
  }
}
