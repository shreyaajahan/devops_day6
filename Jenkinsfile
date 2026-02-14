pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning Terraform Repository...'
                git branch: 'main', url: 'https://github.com/shreyaajahan/devops_day6.git'
            }
        }

        stage('Terraform') {
            steps {
                echo 'Deploying...'
                sh '''
                    terraform init
                    terraform plan -var="ami_id=ami-0b6c6ebed2801a5cb"
                    terraform apply -var="ami_id=ami-0b6c6ebed2801a5cb" -auto-approve
                '''
            }
        }
    }
}
