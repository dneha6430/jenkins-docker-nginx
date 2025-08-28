pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/dneha6430/jenkins-docker-nginx.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-nginx-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                  docker stop my-nginx || true
                  docker rm my-nginx || true
                  docker run -d --name my-nginx -p 9090:80 my-nginx-site
                '''
            }
        }
    }
}
