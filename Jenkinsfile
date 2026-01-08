pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-project', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://1B5B334DD7888422692B344FE6703958.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-project', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://1B5B334DD7888422692B344FE6703958.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
