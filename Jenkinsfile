pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Repository ready'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building application...'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running tests...'
            }
        }

    }
}