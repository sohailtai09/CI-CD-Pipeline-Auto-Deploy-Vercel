pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('VERCEL_TOKEN')
    }

    stages {
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Skipping tests - no test script found'
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                bat 'set APPDATA=C:\\Users\\owaiz\\AppData\\Roaming'
                bat 'set PATH=%PATH%;C:\\Users\\owaiz\\AppData\\Roaming\\npm'
                bat 'vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    }
}