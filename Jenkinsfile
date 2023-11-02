pipeline{
     tools{
	maven 'maven3.9'
        jdk 'java11'
     }
agent any

stages{
  stage('1.CloneRepo'){
     steps{
        git 'https://github.com/Sonal0409/DevOpsClassCodes.git'
     }
  }
  stage('2.build the code'){
     steps{
	sh 'mvnclean install -P metrics pmd:pmd'
     }
  }
}
}
	     
