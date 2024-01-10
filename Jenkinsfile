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
                script {
                    sh 'which node'  // Print the location of the node executable
                    sh 'which npm'   // Print the location of the npm executable
                    sh 'npm --version'  // Print npm version
                    sh 'npm install'
            }
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
