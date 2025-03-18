pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    deleteDir()  // Clean workspace before pulling new code
                    checkout scm
                }
            }
        }
        stage('Build') {
            steps {
                sh 'ls -l'   // Debug: List files in workspace
                sh 'g++ -o hello_exec hello.cpp'
            }
        }
        stage('Test') {
            steps {
                sh './hello_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
