pipeline {
  agent any
    
  tools {nodejs "nodejs"}
    
  stages {

    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
     
//     stage('Build') {
//       steps {
//          sh 'npm run build'
//       }
//     } 
    stage('quality check via sonarqube') {
      steps {
         script{
         def scannerHome = tool 'sonarqube';
             withSonarQubeEnv("sonarqube"){
               sh "${tool("sonarqube")}/bin /sonar-scanner \
                 -Dsonar.projectKey=demo-1 \
                 -Dsonar.sources=. \
                 -Dsonar.host.url=http://172.17.0.1:9000/ \
                 -Dsonar.login=fc7c38c09fc2479f0a53403c7ed0b0ee9858927e"
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
