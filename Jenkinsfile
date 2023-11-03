pipeline{
     tools{
	jdk 'java11'
	maven 'maven3.9'
     }

agent any

stages{
   stage('1.clone the repo'){
      steps{
	 git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
      }
   }

   stage('2.build the code'){
      steps{
         sh 'mvn clean install -P metrics pmd:pmd'
      }
   }
}
}
	  
	     
