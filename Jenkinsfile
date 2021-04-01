pipeline {
    environment {
        registry = "cuongnm3061997/jenkins-demo"
        registryCredential = "docker-keys"
        dockerImage = ''
    }
    agent { label 'dev2' }
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
            }
        }
        stage('Build stage') {
            steps{
                script {
                dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }
        stage('DockerHub stage') {
            steps {
                script {
                    docker.withRegistry( '', registryCredential ) {
                        dockerImage.push()
                    }
                }
            }
        }
    }
}