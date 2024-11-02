pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Pull the code from GitHub
                git branch: 'main', url: 'https://github.com/v4224/static-web.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Assuming you have a package manager; otherwise skip
                script {
                    if (fileExists('package.json')) {
                        sh 'npm install'
                    } else {
                        echo 'No dependencies to install'
                    }
                }
            }
        }

        stage('Build') {
            steps {
                // Example build step for static site generators
                // Use the right command based on your project
                sh 'npm run build'  // For example, if you use npm to build
            }
        }

        stage('Test') {
            steps {
                // Add any test commands here, or skip if none
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy to a server or a static site host
                echo 'Deploying to production...'
                // e.g., `sh 'scp -r ./dist user@yourserver:/var/www/html'`
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
