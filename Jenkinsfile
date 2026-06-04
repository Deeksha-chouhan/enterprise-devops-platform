pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Source code already available'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'cd app && docker build -t enterprise-devops-app:v1 .'
            }
        }

        stage('List Images') {
            steps {
                sh 'docker images'
            }
        }
    }
}
