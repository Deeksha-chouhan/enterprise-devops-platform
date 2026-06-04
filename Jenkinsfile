pipeline {
    agent any

    tools {
        sonarRunner 'SonarScanner'
    }

    stages {

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                    sonar-scanner \
                    -Dsonar.projectKey=enterprise-devops-platform \
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
