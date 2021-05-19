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
    stage('quality check via sonarqube') {
      steps {
         script{
          def scannerHome = tool 'sonarqube';
              withSonarQubeEnv("SonarQube"){
                sh "${tool("sonarqube")}/bin/sonar-scanner\
                -Dsonar.projectKey=my-project-demo\
                -Dsonar.sources=.\
                -Dsonar.host.url=http://127.0.0.1:9000\
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
