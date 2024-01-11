pipeline {
    agent any

    environment {
        PATH = "/usr/bin/npm"
    }

        stage('Install Dependencie') {
            steps {
                script {
                    // Install create-react-app globally without sudo
                    npmInstallGlobal('create-react-app')
                    
                    // Install project dependencies
                    npmInstallLocal()
                }
            }
        }

        stage('Build React Application') {
            steps {
                // Create a new React app using create-react-app
                sh 'npx create-react-app hello-world-example'
            }
        }

        stage('Start App') {
            steps {
                // Change to the app's directory and start the app
                sh 'cd hello-world-example && npm start'
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

    // Custom function to install npm packages globally
    def npmInstallGlobal(package) {
        sh "npm install -g $package"
    }

    // Custom function to install npm packages locally
    def npmInstallLocal() {
        sh 'npm install'
    }
}


