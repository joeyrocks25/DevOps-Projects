pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        S3_BUCKET = 'kp-test-bucket-1'
    }

    stages {
        stage('Build') {
            steps {
                bat 'npm install'
                bat 'npm run build'
                bat 'dir'
                bat 'cd build && dir'
            }
        }
        stage('S3 Upload') {
            steps {
                bat 'dir build'
                bat 'aws s3 cp build s3://$S3_BUCKET/ --recursive'
            }
        }
    }
}
