pipeline {
    agent any

    environment {
        // Ensure Node.js is in PATH (adjust path if Node.js is installed elsewhere)
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
                // Run build command (defined in package.json)
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo "🧪 Running tests..."
                // Optional: if you have test scripts defined
                bat 'npm test'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "📁 Archiving built files..."
                // Assuming
