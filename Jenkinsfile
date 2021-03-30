pipeline {
    agent { label 'slave' }
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
            }
        }
        stage('Build stage') {
            steps {
                sh 'sudo docker build -t nodejs-todolist .'
            }
        }
    }
}