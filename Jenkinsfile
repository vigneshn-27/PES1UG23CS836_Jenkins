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
                sh 'ls -l main'   // Debug: List files in "main" directory
                sh 'g++ -o main/hello_exec main/hello.cpp'  // Compile from "main" folder
            }
        }
        stage('Test') {
            steps {
                sh './main/hello_exec'  // Run the compiled program
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
