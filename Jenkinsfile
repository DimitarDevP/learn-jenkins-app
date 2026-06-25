pipeline {
    agent any
    stages {
        stage('w/o docker') {
            steps {
                sh 'echo "Without Docker"'
            }
        }
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh 'echo "With docker"'
                sh 'npm --version'
                sh 'npm run build'
                sh 'npm start'
            }
        }
    }
}