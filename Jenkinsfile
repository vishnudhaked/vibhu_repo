pipeline {
    agent any

    stages {
        stage('Install create-react-app') {
            steps {
                script {
                    // Run the npm install command
                    sh 'npm install -g create-react-app'
                }
            }
        }

        // Add more stages as needed for your pipeline
    }

    post {
        success {
            echo 'create-react-app installed successfully.'
        }
        failure {
            echo 'Failed to install create-react-app.'
        }
    }
}


