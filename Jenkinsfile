pipeline {
    agent { label 'dev' }
    stages {
        stage('Clone stage') {
            steps {
                git 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
            }
        }
        stage('Build stage') {
            steps {
                sh 'docker build -t nodejs-todolist .'
                sh 'docker run -d --name jenkinsContainer -p 8080:8080 nodejs-todolist '
            }
        }
    }
}