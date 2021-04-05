pipeline {
    environment {
        registry = "cuongnm3061997/jenkins-demo-1"
        registryCredential = "docker-keys"
        dockerImage = ''
    }
    agent { label 'dev2' }
    stages {
        stage('Clone stage') {
            steps {
                // git 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
                git branch: 'dev', url: 'https://github.com/nguyencuong30697/jenkin-nodejs-demo.git'
            }
        }
        stage('Build stage') {
            steps{
                script {
                    dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }
        // stage('Push Image stage') {
        //     steps {
        //         script {
        //             docker.withRegistry( '', registryCredential ) {
        //                 dockerImage.push()
        //             }
        //         }
        //     }
        // }
        // stage('Run Docker Image') {
        //     steps{
        //         sh "docker run --rm -p 8180:8080 $registry:$BUILD_NUMBER"
        //     }
        // }
        // stage('Remove Unused Docker Image') {
        //     steps{
        //         sh "docker rmi $registry:$BUILD_NUMBER"
        //     }
        // }
    }
}