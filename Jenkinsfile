pipeline {
    tools {
        nodejs 'nodejs'
    }
    agent any
    environment {
        registry = "619071355982.dkr.ecr.eu-west-2.amazonaws.com/my-test-repo"
    }

    stages {
        
        stage('Building the project') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t repo-jan-2025-api .'
            }
        }
        
        stage('Tag Docker Image') {
            steps {
                sh 'docker tag repo-jan-2025-api:latest 619071355982.dkr.ecr.eu-west-2.amazonaws.com/my-test-repo:$BUILD_NUMBER'
            }
        }

        stage('Pushing to ECR') {
        steps{  
            script {
                    sh 'aws ecr get-login-password --region eu-west-2 | docker login --username AWS --password-stdin 619071355982.dkr.ecr.eu-west-2.amazonaws.com/my-test-repo'
                    sh 'docker push 619071355982.dkr.ecr.eu-west-2.amazonaws.com/my-test-repo:$BUILD_NUMBER'
            }
            }
      }
    }
}
