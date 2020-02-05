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
      stage('Email Build Status') {
      steps {
         mailbody:"${env.JOB_NAME} - Build # ${env.BUILD_NUMBER} - ${currentBuild.currentResult} \n\nCheck console output at ${env.BUILD_URL} to view the results.",subject:"${env.JOB_NAME} -Build #${env.BUILD_NUMBER} -${currentBuild.currentResult}!!",to:'sreenivas261988@gmail.com'
    }
   }
  }
} 
