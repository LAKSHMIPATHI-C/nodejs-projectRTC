pipeline {
    agent any

    environment {
        PATH = "C:\\Program Files\\nodejs;${PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "🔁 Cloning Node.js project from GitHub..."
                git branch: 'main', url: 'https://github.com/LAKSHMIPATHI-C/nodejs-projectRTC.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "📦 Installing npm dependencies..."
                bat 'npm install'
            }
        }

        stage('Run App') {
            steps {
                echo "🚀 Starting Node.js application..."
                bat 'npm start || echo No start script found'
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed. Check logs for details."
        }
        always {
            echo "🧹 Cleaning workspace..."
            cleanWs()
        }
    }
}

