pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-credencial', toolName: 'docker') {
                        sh "docker build -t shivaangata/shippingservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-credencial', toolName: 'docker') {
                        sh "docker push shivaangata/shippingservice:latest "
                    }
                }
            }
        }
    }
}
