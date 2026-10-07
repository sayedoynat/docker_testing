pipeline {
    agent {
        label 'docker'
    }
 
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t sayedoynat/docker-react -f dockerfile.dev .'
                }
            }
        }
 
        stage('Tests') {
            steps {
                script {
                    env.DOCKER_BUILDKIT = 1
                    sh 'docker run -e CI=true sayedoynat/docker-react npm run test'
                }
            }
        }
    }
}