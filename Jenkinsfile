pipeline {
    agent any
    
    environment {
        // Define environment variables
        XAMPP_INSTALL_DIR = 'C:/xampp/htdocs' // Adjust the path to your XAMPP installation directory
        GITHUB_REPO_URL = 'https://github.com/Bhramanand/Java.git' // Replace with your GitHub repository URL
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the GitHub repository
                git branch: 'main', url: "${env.GITHUB_REPO_URL}"
            }
        }

        stage('Deploy to XAMPP') {
            steps {
                // Copy HTML files to XAMPP htdocs directory
                bat "xcopy /E /Y .\\ ${env.XAMPP_INSTALL_DIR}"
            }
        }

        stage('Post-deployment Tests') {
            steps {
                // Perform any post-deployment tests or validations here
                // For example, you could use curl or Selenium to test the deployed web pages
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
            // Optionally, you can trigger downstream jobs or notifications here
        }
        failure {
            echo 'Deployment failed!'
            // Optionally, you can trigger notifications or take corrective actions here
        }
    }
}


