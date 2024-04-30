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
                sh 'javac Addition.java'
            }
        }

        stage('Test') {
            steps {
                // Execute the Java program
                sh 'java Addition'
            }
        }
    }
}

