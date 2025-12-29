pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo '=== Checking out code from GitHub ==='
                checkout scm
            }
        }
        
        stage('List Files') {
            steps {
                echo '=== Repository Contents ==='
                sh 'ls -la'
                sh 'find . -name "*.java"'
            }
        }
        
        stage('Build') {
            steps {
                echo '=== Building Java Files ==='
                script {
                    // Find and compile Java files
                    sh '''
                        if [ -d "src" ]; then
                            echo "Compiling Java files in src directory..."
                            javac src/*.java || echo "Add your build commands here"
                        else
                            echo "No src directory found"
                        fi
                    '''
                }
            }
        }
        
        stage('Test') {
            steps {
                echo '=== Running Tests ==='
                sh 'echo "Add your test commands here"'
            }
        }
        
        stage('Deploy') {
            steps {
                echo '=== Deployment Stage ==='
                sh 'echo "Add deployment steps here"'
            }
        }
    }
    
    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}
