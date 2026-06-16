pipeline {
    agent any

    stages {

        stage('Clean Workspace') {
            steps {
                sh 'rm -rf .terraform'
                sh 'rm -rf .terraform.lock.hcl'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init -reconfigure'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }

        stage('Output') {
            steps {
                sh 'terraform output'
            }
        }
    }
}
