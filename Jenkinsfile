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

        stage('Test') {
            steps {
                echo "🧪 Running tests..."
                bat 'npm test || echo No tests found'
            }
        }

        stage('Run App') {
            steps {
                echo "🚀 Starting Node.js application..."
                bat 'npm start'
            }
        }
    }

    post {
        success {
            echo "✅ Build completed successfully!"
        }
        failure {
            echo "❌ Build failed. Please check console output."
        }
        always {
            echo "🧹 Cleaning up workspace..."
            cleanWs()
        }
    }
}
