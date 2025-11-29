pipeline {
    agent any

    tools {
        terraform 'Terraform'
    }

    stages {

        stage('Git Checkout') {
            steps {
                echo 'Cloning project codebase...'
                git branch: 'main', url: 'https://github.com/devopsmike-01/jenkins-terraform-infra-repo.git'
                sh 'ls -al'
            }
        }

        stage('Verify Terraform Version') {
            steps {
                echo 'Checking terraform version...'
                sh 'terraform --version'
            }
        }

        stage('Terraform Init') {
            steps {
                echo 'Initializing terraform...'
                sh 'terraform init'
            }
        }

        stage('Terraform Validate') {
            steps {
                echo 'Validating terraform syntax...'
                sh 'terraform validate'
            }
        }

        stage('Terraform Plan (Dry Run)') {
            steps {
                echo 'Showing Terraform plan (no deployment)...'
                sh 'terraform plan'
            }
        }
    }
}
