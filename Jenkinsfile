pipeline {
agent any

```
stages {

    stage('Checkout') {
        steps {
            git branch: 'main',
                url: 'https://github.com/Deeksha-chouhan/enterprise-devops-platform.git'
        }
    }

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
                }
            }
        }
    }

    stage('Docker Build') {
        steps {
            sh '''
                docker build -t 9691427913/enterprise-devops-platform:latest ./app
            '''
        }
    }

    stage('Docker Push') {
        steps {
            withCredentials([usernamePassword(
                credentialsId: 'dockerhub-creds',
                usernameVariable: 'DOCKER_USER',
                passwordVariable: 'DOCKER_PASS'
            )]) {
                sh '''
                    echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                    docker push 9691427913/enterprise-devops-platform:latest
                '''
            }
        }
    }
}
```

}

