pipeline {
    agent any

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
