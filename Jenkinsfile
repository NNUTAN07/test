pipeline{

    tools{
       maven 'maven3.9'
       jdk 'java11'
    }
 
    agent any

    stages{

       stage('1.CloneRepo')
        {
           
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }


      stage('2.Build the code){
         steps{
            sh 'clean install -P metrics pmd:pmd'
            }
             }
  }
}
