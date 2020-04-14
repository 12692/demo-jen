pipeline {
  agent any
  stages {
    stage('Build Application') { 
      steps {
      echo 'mvn install ...'
        bat 'mvn clean install'
      }
    }
 	stage('Test') { 
      steps {
        echo 'Test Appplication...' 
      }
    }
 	
    stage('Deploy CloudHub') { 
    	      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
       steps {
        echo 'Deploying only because this commit is tagged...'
        bat 'mvn package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denvironment=Sandbox -DmuleVersion=4.2.2' 
      }
    }
  }
}