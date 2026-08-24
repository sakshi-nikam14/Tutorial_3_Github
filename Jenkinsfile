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
                bat '"C:\\Users\\saksh\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t tut5 .'
            }
        }

        stage('Deploy') {
            steps {
                bat '"C:\\Users\\saksh\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" stop containertut5 || exit 0'
                bat '"C:\\Users\\saksh\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" rm containertut5 || exit 0'
                bat '"C:\\Users\\saksh\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" run -d -p 5000:5000 --name containertut5 tut5'
            }
        }
    }
}
