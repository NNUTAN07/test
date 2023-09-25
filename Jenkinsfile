Complete CICD pipeline
go to vim /etc/sudoers

add this line

Jenkins ALL=NOPASSWD: ALL

Change permissions for jenkins to run docker commands:
chmod 777 /var/run/docker.sock

pipeline{
    tools{
        maven 'maven3.9'
    }
    agent any
    stages{
        stage('clone repo'){
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        stage('build the code'){
            steps{
                sh 'mvn clean install package'
                
            }
        }
        
        stage('Build Image'){
            steps{
               sh 'docker build -t myimagejenkins .'
            }
        }
        stage('Push image to dockerhub'){
            steps{
                sh 'docker tag myimagejenkins edu123/myimagejenkins:$BUILD_NUMBER'
                sh 'docker login --username edu123 --password Edureka@123'
                sh 'docker push edu123/myimagejenkins:$BUILD_NUMBER'
            }
        }
        
       
    }
}
