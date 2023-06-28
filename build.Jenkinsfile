pipeline {
    agent any
     environment {
        
        AWS_REGION = 'us-west-1'
        ECR_REGISTRY_URL = '854171615125.dkr.ecr.us-west-1.amazonaws.com/sangini-jenkins-repo'
    }
    stages {
        stage('Build Yolo5 app') {
            dir(D:\jenkins\app_development_I\yolo5) {
                sh "pwd"
                    }
            steps {
                sh '''
                    aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 854171615125.dkr.ecr.us-west-1.amazonaws.com
                    docker build -t sangini-jenkins-repo .
                    docker tag sangini-jenkins-repo:latest 854171615125.dkr.ecr.us-west-1.amazonaws.com/sangini-jenkins-repo:latest
                    docker push 854171615125.dkr.ecr.us-west-1.amazonaws.com/sangini-jenkins-repo:latest
                '''
                }
            }
        }
    }
    
