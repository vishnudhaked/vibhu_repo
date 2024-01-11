pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Assuming your React.js project is hosted on GitHub
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install create-react-app globally
                    sh 'sudo npm install -g create-react-app'
                    
                    // Install project dependencies
                    sh 'sudo npm install -s'
                }
            }
        }

        stage('Build React Application') {
            steps {
                // Create a new React app using create-react-app
                sh 'sudo npx create-react-app hello-world-example'
            }
        }

        stage('Start App') {
            steps {
                // Change to the app's directory and start the app
                sh 'sudo cd hello-world-example && npm start'
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

