pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-credential', toolName: 'docker') {
                        sh "docker build -t shivaangata/recommendationservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-credential', toolName: 'docker') {
                        sh "docker push shivaangata/recommendationservice:latest "
                    }
                }
            }
        }
    }
}
