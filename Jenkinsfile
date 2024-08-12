pipeline {
    agent any

    environment {
        ECR_REPO_URI = 'your-account-id.dkr.ecr.us-east-1.amazonaws.com/your-repo'
        IMAGE_TAG = "latest"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Iam-Manirathnam/task_Mani.git'
            }
        }

        stage('Terraform initialise') {
            steps {
                script {
                    sh 'terraform init'
                }
            }
        }

        stage('terraform plan') {
            steps {
                script {
                    sh 'terraform plan'
                }
            }
        }

        stage('terraform apply') {
            steps {
                script {
                    sh 'terraform apply -auto-approve'
                }
            }
        }

    }

    post {
        always {
            cleanWs()
        }
    }
}
