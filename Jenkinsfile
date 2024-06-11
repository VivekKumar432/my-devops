pipeline {
    agent any

    tools {
        nodejs "NodeJS"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/VivekKumar432/my-devops.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("myapp:${env.BUILD_ID}")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.run("-p 3000:3000")
                }
            }
        }
    }
}
