pipeline {
  agent any 
    environment {
      S3_BUCKET= 'devops2026pipelinefriday'
    }
        
    stages {
      stage('Checkout') {
        steps {
          git branch: 'main', url:"https://github.com/sachinpriyadiyadisha929-dotcom/nodejs-demoapp.git"
        }
      }
      stage('Build') {
        steps {
          sh 'npm install'
          sh 'npm run build'
        }
      }
      stage('Deploy on S3') {
        steps {
          sh '''
          aws s3 cp ./dist s3://$S3_BUCKET/ --recursive
          '''
        }
      }
    }
}
          
