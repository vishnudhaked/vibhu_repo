pipeline {
    agent any

    stages {
        stage('Install Node.js and create-react-app') {
            steps {
                script {
                    // Install NVM
                    sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash'
                    sh 'source ~/.bashrc'

                    // Install Node.js using NVM
                    sh 'nvm install node'

                    // Install create-react-app
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



