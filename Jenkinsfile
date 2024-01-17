pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Install Node.js and create-react-app') {
            steps {
                script {
                    // Install Node.js using NVM
                    sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash'
                    sh 'export NVM_DIR="$HOME/.nvm" && [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" && nvm install node'
                    
                    // Install create-react-app globally
                    sh 'sudo npm install -g create-react-app -s'
                }
            }
        }
        
        stage('Create React App') {
            steps {
                script {
                    // Create a new React app
                    sh 'sudo npx create-react-app hello-world-example -s'
                }
            }
        }
    }
}







