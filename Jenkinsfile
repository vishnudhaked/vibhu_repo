pipeline {
    agent any
    tools {
        nodejs 'nodejs'
    }

    stages {
        stage('Build') {
            steps {
                checkout scm
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm run test'
                echo 'Test'
            }
        }

        stage('Building Image') {
            steps {
                sh 'docker build -t reactimage .'
                sh 'docker tag reactimage:latest cloud01/dev:latest'
            }
        }

        stage('Docker login') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'Dockercred', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                    sh "echo $PASS | docker login -u $USER --password-stdin"
                    sh 'docker push cloud01/dev:latest'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    def dockerCmd = 'docker run -itd --name react_container -p 3000:3000 cloud01/dev:latest'
                    sshagent(['sshkeypair']) {
                        sh "ssh -o StrictHostKeyChecking=no ubuntu@34.238.155.217 ${dockerCmd}"
                    }
                }
            }
        }
    }
}


