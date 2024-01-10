pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your Git repository
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Build the React.js application
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                // Run tests if applicable
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Example: Deploy to a web server or push to a cloud service
                // Adjust this stage based on your deployment needs
            }
        }
    }

    post {
        success {
            // Additional post-build actions on success
            echo 'Build and deployment successful!'
        }
        failure {
            // Additional post-build actions on failure
            echo 'Build and deployment failed!'
        }
    }
}
