pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker build . -t flask --no-cache
            }
        }
        stage('Tag and push to container registry') {
            steps {
                docker tag flask:latest tp4terraform.azurecr.io/flask-app
                docker push tp4terraform.azurecr.io/flask-app
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}