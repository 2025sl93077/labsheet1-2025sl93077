pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/2025sl93077/labsheet1-2025sl93077'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Building application..."'
                sh 'python3 --version'
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Running tests..."
                python3 test_calculator.py
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Deploying to EC2..."
                scp -o StrictHostKeyChecking=no calculator.py ubuntu@<EC2-IP>:/home/ubuntu/
                '''
            }
        }
    }
}
