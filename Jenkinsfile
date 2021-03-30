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
                sh 'docker build -t nodejs-todolist3 .'
                sh 'docker run -d --name abc111333 -p 8083:8080 nodejs-todolist3 '
            }
        }
    }
}