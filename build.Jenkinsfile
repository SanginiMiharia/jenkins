pipeline {
    agent any
     environment {
        
        AWS_REGION = 'us-west-1'
        ECR_REGISTRY_URL = '854171615125.dkr.ecr.us-west-1.amazonaws.com/sangini-jenkins-repo'
    }
    stages {
        stage('Build Yolo5 app') {
            steps {
                sh '''
                    aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 854171615125.dkr.ecr.us-west-1.amazonaws.com
                    cd yolo5 
                    docker build -t sangini-jenkins-repo .
                    docker tag sangini-jenkins-repo:latest 854171615125.dkr.ecr.us-west-1.amazonaws.com/sangini-jenkins-repo:${BUILD_NUMBER}
                    docker push 854171615125.dkr.ecr.us-west-1.amazonaws.com/sangini-jenkins-repo:${BUILD_NUMBER}
                '''
                }
            }
        }
    }
    
