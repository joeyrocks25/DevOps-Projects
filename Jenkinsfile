pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        S3_BUCKET = 'kp-test-bucket-1'
        GITHUB_CREDENTIALS = credentials('GITHUB_CREDENTIALS')
    }

    stages {
        stage('Checkout') {
            steps {
                git(
                    url: 'https://github.com/joeyrocks25/DevOps-Projects.git',
                    branch: 'main',
                    credentialsId: 'GITHUB_CREDENTIALS'
                )
            }
        }
        stage('S3 Upload') {
            steps {
                bat 'dir'
                bat 'aws s3 cp Week1/index.html s3://%S3_BUCKET%/index.html'
                bat 'aws s3 cp Week1/style.css s3://%S3_BUCKET%/style.css'
            }
        }
    }
}
