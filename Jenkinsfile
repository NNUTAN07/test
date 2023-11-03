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
   stage('3.build the image'){
      steps{
	 sh 'sudo docker build -t testimage .'
      }
   }
   stage('4.push to docker hub'){
      steps{
	 sh 'sudo docker tag testimage nutan69/declarative:$BUILD_NUMBER'
	 sh 'sudo docker login -u nutan69 -p nutanni@69'
	 sh 'sudo docker push nutan69/declarative:$BUILD_NUMBER'
      }
   }
}
}
	  
	     
