pipeline {
    agent any

    environment {
        // Ensure Node.js is in PATH (adjust if installed elsewhere)
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

        stage('Build') {
            steps {
                echo "🏗️ Building Node.js project..."
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo "🧪 Running tests..."
                bat 'npm test'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "📁 Archiving built files..."
                archiveArtifacts artifacts: 'dist/**/*.*', fingerprint: true
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
