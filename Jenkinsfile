pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Sukesh-git-889/sudo-docker-run-hello-world.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Deploy Application') {
            steps {
                sh '''
                    docker rm -f myapp || true
                    docker run -d --name myapp -p 8081:80 myapp:latest
                '''
            }
        }
    }
}
