pipeline {
    agent any

    stages {
        stage('Install create-react-app') {
            steps {
                script {
                    // Run npm install -g create-react-app
                    sh 'npm install -g create-react-app'
                }
            }
        }

        // Add more stages as needed
    }

    post {
        always {
            // Cleanup or additional steps to execute always
        }
    }
}






