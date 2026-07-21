pipeline {

    agent any

    environment {
        IMAGE_NAME = "fastapi-cicd"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Show Environment') {
            steps {
                sh '''
                    pwd
                    ls -la
                    docker --version
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                    docker build -t ${IMAGE_NAME}:${IMAGE_TAG} .
                '''
            }
        }

        stage('List Docker Images') {
            steps {
                sh '''
                    docker images
                '''
            }
        }

    }

    post {

        success {
            echo "Pipeline Success ✅"
        }

        failure {
            echo "Pipeline Failed ❌"
        }

    }

}