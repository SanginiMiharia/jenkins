pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                
                sh '''
                aws eks --region us-east-2 update-kubeconfig --name k8s-batch1
                kubectl config set-context --current --namespace=sangini
                cd k8s
                kubectl apply -f yolo5.yaml
                '''
            }
        }
    }
}