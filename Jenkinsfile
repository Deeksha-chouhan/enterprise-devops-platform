pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Deeksha-chouhan/enterprise-devops-platform.git'
            }
        }
<<<<<<< HEAD

       stage('SonarQube') {
    steps {
        withSonarQubeEnv('SonarQube') {
            withCredentials([string(credentialsId: 'sonar-token', variable: 'SONAR_AUTH_TOKEN')]) {
                sh '''
                    /opt/sonar-scanner/bin/sonar-scanner \
                    -Dsonar.projectKey=enterprise-devops-platform \
                    -Dsonar.sources=. \
                    -Dsonar.host.url=http://172.16.233.129:9001 \
                    -Dsonar.login=$SONAR_AUTH_TOKEN
                '''
=======
                """
>>>>>>> fc2d7a4 (Fix SonarQube project key)
            }
        }
    }
}
