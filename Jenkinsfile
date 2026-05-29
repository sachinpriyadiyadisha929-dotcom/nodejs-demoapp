pipeline {

    agent any


    environment {
        S3_BUCKET = "devops2026pipelinefriday"
        AWS_DEFAULT_REGION = "ap-south-1"
    }

    stages {

        stage('Checkout') {

            steps {

                git branch: 'main', url: 'https://github.com/sachinpriyadiyadisha929-dotcom/nodejs-demoapp.git'

            }

        }


        stage('Build') {

            steps {

        sh 'npm install'
        sh 'npm run build'

            }

        }

        stage('Deploy to S3') {
            steps {
                    sh '''
                    aws s3 sync dist/ s3://$S3_BUCKET --delete
                    '''
                }
            }
        }
    }

