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
    }
}


