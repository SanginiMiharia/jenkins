pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                
                sh '''
                cd app_development_I
                cd k8s
                kubectl apply -f yolo5.yaml
                '''
            }
        }
    }
}