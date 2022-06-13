pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
        
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
        
    stage('Install dependencies') {
      steps {
	    sh 'npm config set registry http://registry.npmjs.org/'
        sh 'npm install'
      }
    }
     
    stage('Test') {
      steps {
         sh 'npm test'
      }
    }      
  }
}
