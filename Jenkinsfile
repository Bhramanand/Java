pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Bhramanand/Java.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'javac Addition.java'
            }
        }
        
        stage('Test') {
            steps {
                sh 'java Addition'
            }
        }
    }
}
