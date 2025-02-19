pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        S3_BUCKET = 'kp-test-bucket-1'
    }

    stages {
        stage('S3 Upload') {
            steps {
                sh 'dir'
                sh 'pwd'
                bat 'aws s3 cp Week1/Solution/index.html s3://$S3_BUCKET/Week1/index.html'
                bat 'aws s3 cp Week1/Solution/style.css s3://$S3_BUCKET/Week1/style.css'
            }
        }
    }
}
