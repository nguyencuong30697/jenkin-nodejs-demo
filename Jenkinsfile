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
                sh 'docker build -t nodejs-todolist1 .'
                sh 'docker run -d --name abc1112222 -p 8081:8080 nodejs-todolist1 '
            }
        }
    }
}