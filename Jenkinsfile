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
                // Step 1: Checkout the source code from the GitHub repository
                git branch: 'main', url: "${env.GITHUB_REPO_URL}"
            }
        }

        stage('Deploy to XAMPP') {
            steps {
                // Step 2: Copy HTML files to XAMPP htdocs directory
                bat "xcopy /E /Y .\\* ${env.XAMPP_INSTALL_DIR}"
            }
        }

        stage('Post-deployment Tests') {
            steps {
                // Step 3: Perform any post-deployment tests or validations here
                // For example, you could use curl or Selenium to test the deployed web pages
                script {
                    // Example: Use curl to test if the homepage is accessible
                    sh "curl -Is http://localhost/index.html | head -n 1"
                    
                    // Example: Use Selenium to perform automated UI testing
                    // This requires additional setup and installation of Selenium WebDriver
                }
            }
        }
    }

    post {
        success {
            // Step 4: Actions to be taken if deployment is successful
            echo 'Deployment successful!'
            // Optionally, you can trigger downstream jobs or notifications here
        }
        failure {
            // Step 5: Actions to be taken if deployment fails
            echo 'Deployment failed!'
            // Optionally, you can trigger notifications or take corrective actions here
        }
    }
}



