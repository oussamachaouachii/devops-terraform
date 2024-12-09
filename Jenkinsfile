pipeline {
    agent any

    stages {
        
        stage('Build') {
            steps {
                sh 'docker build . -t flask --no-cache'
            }
        }
        stage('Tag image') {
            steps {
                sh 'docker tag flask:latest tp4terraform.azurecr.io/flask-app'
                sh 'docker push tp4terraform.azurecr.io/flask-app'
            }
        }
        stage('Testing') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh 'terraform init'
                sh 'terraform apply --auto-approve'
            }
        }
    }
}