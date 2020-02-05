pipeline {
agent any 
stages {
   stage('Cleaning Stage') {
      steps {
      sh 'mvn clean'
    }
   } 
   stage('Testing stage') {
      steps {
      sh 'mvn test'
      }
     }
   stage('Packaging stage') {
      steps {
      sh 'mvn package' 
      }
     }
   stage('Results') {
      steps {
      input ("Do you want to generate reports?")
      junit '**/target/surefire-reports/TEST-*.xml'
     }
   } 
   
   
  }
} 
