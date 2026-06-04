pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Deeksha-chouhan/enterprise-devops-platform.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                        sonar-scanner \
                        -Dsonar.projectKey=enterprise-devops \
                        -Dsonar.sources=. \
                        -Dsonar.host.url=http://172.16.233.129:9001 \
                        -Dsonar.login=$SONAR_AUTH_TOKEN
                    '''
                }
            }
        }
    }
}
