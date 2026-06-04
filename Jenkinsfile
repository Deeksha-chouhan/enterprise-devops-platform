pipeline {
    agent any

    stages {

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                    sonar-scanner \
                    -Dsonar.projectKey=enterprise-devops-platform \
                    -Dsonar.projectName=Enterprise-DevOps-Platform \
                    -Dsonar.sources=app
                    '''
                }
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t enterprise-devops-app:v1 app/'
            }
        }

    }
}
