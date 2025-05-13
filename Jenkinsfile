pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/ShreejitNair/pro1.git', branch: "master"
                sh 'mvn clean package'
              
            }
        }

         stage('Install Docker using Ansible') {
            steps {
                sh 'ansible-playbook ansible-playbook.yml'
            }
        }
        
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t shreejitnair2000/staragileprojectfinance:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name My-first-containe21211 -p 8083:8081 shreejitnair2000/staragileprojectfinance:v1'
                  
                }
            }
        
    }
}
