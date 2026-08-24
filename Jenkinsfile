pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat "C:\Users\saksh\AppData\Local\Programs\DockerDesktop\resources\bin\docker.exe ."
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop containertut5 || exit 0'
                bat 'docker rm containertut5 || exit 0'
                bat 'docker run -d -p 5000:5000 --name containertut5 tut5'
            }
        }
    }
}
