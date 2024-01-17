pipeline {
    agent any
    
    stages {
        stage('Install tar latest') {
            steps {
                script {
                    // Use npm to install tar at the latest version globally
                    sh 'npm install -g tar@latest'
                }
            }
        }
        
        stage('Install create-react-app') {
            steps {
                script {
                    // Use npm to install create-react-app globally
                    sh 'npm install -g create-react-app'
                }
            }
        }
        
        stage('Create React App') {
            steps {
                script {
                    // Use npx to create a new React app
                    sh 'npx create









