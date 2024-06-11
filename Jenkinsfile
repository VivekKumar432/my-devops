pipeline {
    agent any

    tools {
        nodejs 'NodeJS' // Name of the Node.js installation in Jenkins
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/VivekKumar432/my-devops.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        // stage('Test') {
        //     steps {
        //         bat 'npm test'
        //     }
        // }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp .'
            }
        }
        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 80:80 myapp'
            }
        }
    }
}
