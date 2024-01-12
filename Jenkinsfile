pipeline {
    agent any

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
pipeline {
agent any
tools {
nodejs *nodejs*
t

stages {
stage(‘Build’) {
steps {
checkout scmGit(branches: [[nane: “*/Dev']], extensions: [],
sh ‘npm install”
7/ sh ‘pm run build
}
}
stage(‘Test’) {
steps (
7/ sh ‘npm run test"
echo “Test”

+

d
stage( ‘Build Image’) {
steps {
sh ‘docker build -t reactimage ."
sh ‘docker tag reactimage:latest cloud0@1/dev:latest’

userRenoteConfigs: [[credentialsId: ‘gitcreds', url
stage(‘Docker login’) {
steps {
withCredentials([usernamePassword(credentialsId: ‘Dockercred", passwordVariable: "PASS", usernameVariable: ‘USER’)]) {
sh “echo $PASS | docker login -u $USER --password-stdin™
sh ‘docker push cloud@01/dev: latest’

t
t
t
stage(‘Deploy") {
steps {
script {
def dockerCmd = ‘docker run -itd --name react_container -p 3000:3000 cloud@@1/dev:latest*
sshagent(["sshkeypair']) {
sh “ssh -o StrictHostKeyChecking-no ubuntu@34.238.155.217 ${dockerCmd}"
t
t
t

