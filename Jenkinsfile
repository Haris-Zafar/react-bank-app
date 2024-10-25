pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code from GitHub...'
                git branch: 'main', url: 'https://github.com/Haris-Zafar/react-bank-app'
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                script {
                    // Install npm dependencies
                    bat 'npm install'
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                script {
                    // Build the application
                    bat 'npm run build'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                script {
                    // Run the test command
                    bat 'npm test'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
