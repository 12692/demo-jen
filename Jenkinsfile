pipeline {
  agent any
  stages {
    stage('Build Application') { 
      steps {
      echo mvn install ...'
        bat 'mvn clean install'
      }
    }
 	stage('Test') { 
      steps {
        echo 'Test Appplication...' 
      }
    }
 	
    stage('Deploy CloudHub') { 
      steps {
        echo 'Deploying only because this commit is tagged...'
        bat 'mvn package deploy -DmuleDeploy' 
      }
    }
  }
}