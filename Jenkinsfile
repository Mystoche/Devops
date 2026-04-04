pipeline {
    agent any
    stages {
        stage('Deploy to Minikube') {
            steps {
                withCredentials([file(credentialsId: 'k8s', variable: 'KUBECONFIG')]) {
                    withEnv(["PATH=$HOME:$PATH"]) {
                        sh 'kubectl version --client'
                        sh 'kubectl get pods'
                        sh 'kubectl apply -f deployment.yaml'
                    }
                }
            }
        }
    }
}
