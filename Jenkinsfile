pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repo-url.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('your-dockerhub-username/studentproject')
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub-credentials', url: '']) {
                    script {
                        docker.image('your-dockerhub-username/studentproject').push('latest')
                    }
                }
            }
        }
    }
}
