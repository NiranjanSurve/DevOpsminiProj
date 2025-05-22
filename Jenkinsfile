pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-third-website .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f third-container || echo "No old container"'
                bat 'docker run -d --name third-container -p 8083:80 devops-third-website'
            }
        }
    }
}
