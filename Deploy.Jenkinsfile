pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                
                sh '''
                cd k8s
                kubectl apply -f yolo5.yaml
                '''
            }
        }
    }
}