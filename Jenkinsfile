pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the GitHub repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Compile the Java program
                try {
                    sh 'javac Addition.java'
                } catch (Exception e) {
                    echo "Build failed: ${e.message}"
                    currentBuild.result = 'FAILURE'
                    error(e.message)
                }
            }
        }

        stage('Test') {
            steps {
                // Execute the Java program
                try {
                    sh 'java Addition'
                } catch (Exception e) {
                    echo "Test failed: ${e.message}"
                    currentBuild.result = 'FAILURE'
                    error(e.message)
                }
            }
        }
    }
}

