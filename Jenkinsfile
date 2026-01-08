pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-project1', contextName: '', credentialsId: 'docker-pass', namespace: 'webapps', serverUrl: 'https://2FE6698E04BFC5669597FFDE6F661780.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-project1', contextName: '', credentialsId: 'docker-pass', namespace: 'webapps', serverUrl: 'https://2FE6698E04BFC5669597FFDE6F661780.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
