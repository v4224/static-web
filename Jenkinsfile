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
                dir('subdirectory-name') { // Replace with the actual subdirectory name where package.json is located
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                dir('subdirectory-name') { // Replace with the actual subdirectory name where package.json is located
                    sh 'npm run build'
                }
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
