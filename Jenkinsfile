pipeline {
    environment {
        registry = "cuongnm3061997/jenkins-demo"
        registryCredential = "docker-hub-cres"
        dockerImage = 'cuongnm3061997'
    }
    agent { label 'dev2' }
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
            }
        }
        stage('Build stage') {
            steps {
                sh 'docker build -t cuongnm3061997/docker-nodejs-jen .'
                // sh 'docker-compose up -d'
            }
        }
        stage('DockerHub stage') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', "docker-hub-cres"){
                        dockerImage.push()
                    }
                }
            }
        }
    }
}