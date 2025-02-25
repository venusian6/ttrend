pipeline {
    agent{
        node{
            label 'maven-slave'
        }
    }
       environment{
             PATH = "/opt/apache-maven-3.9.9/bin:$PATH"
        }

    stages {
        stage('Build') {
            steps {
                
             sh 'mvn clean test'
                }
        }

  stage('SonarQube analysis') {

    environment{scannerHome = tool 'my-sonar-scanner'
   }
   steps{

   
      withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"}
    }
  }
        
    }
}