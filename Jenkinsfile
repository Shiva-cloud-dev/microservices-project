pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-pass', toolName: 'docker') {
                        sh "docker build -t shivaangata/emailservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-pass', toolName: 'docker') {
                        sh "docker push shivaangata/emailservice:latest "
                    }
                }
            }
        }
    }
}
