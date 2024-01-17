pipeline {
    agent any

    stages {
        stage('Install create-react-app') {
            steps {
                script {
                    // Install create-react-app globally
                    sh 'npm install -g create-react-app'
                }
            }
        }

        stage('Create React App') {
            steps {
                script {
                    // Create a new React app
                    sh 'npx create-react-app hello-world-example'
                }
            }
        }
    }

    post {
        always {
            // Clean up or post-build steps if needed
        }
    }
}








