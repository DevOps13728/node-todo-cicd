pipeline {
    agent any
    
    stages{
        stage('Code'){
            steps{
                git url: 'https://github.com/DevOps13728/node-todo-cicd.git', branch: 'master' 
            }
        }
        stage('Build and Test'){
            steps{
                sh 'docker stop testjob2_web_1 && docker rm testjob2_web_1 && docker rmi testjob2_web && docker build . -t DevOps13728/node-todo-test:latest'
            }
        }
        stage('Deploy'){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
