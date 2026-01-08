pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-pass', toolName: 'docker') {
                        sh "docker build -t shivaangata/adservice:v1 ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-pass', toolName: 'docker') {
                        sh "docker push shivaangata/adservice:v1 "
                    }
                }
            }
        }
    }
}
