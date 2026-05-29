pipeline {
    agent any

    tools {
        nodejs 'nodejs'
    }

    environment {
        S3_BUCKET = 'devops2026pipelinefriday'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/sachinpriyadiyadisha929-dotcom/nodejs-demoapp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Deploy to S3') {
            steps {
                sh '''
                aws s3 sync . s3://$S3_BUCKET --delete
                '''
            }
        }
    }
}
