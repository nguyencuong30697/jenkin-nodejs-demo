pipeline {
    agent { label 'dev2' }
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
            }
        }
        stage('Build stage') {
            steps {
                sh 'docker build -t docker-nodejs-jen .'
                sh 'docker-compose up -d'
            }
        }
    }
}