pipeline {
agent any 
stages {
   stage('Parallel Pipeline') {
      steps {
         Parallel(
            a:{
               sh 'mvn clean'
               }
            c:{
               sh 'mvn package'
                }
            )
         }
   }
}
   stage('Results') {
      steps {
      input ("Do you want to generate reports?")
      junit '**/target/surefire-reports/TEST-*.xml'
     }
   } 
  }

