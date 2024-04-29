pipeline {
    agent any
    
    triggers {
        cron('*/2 * * * *') // Run every 2 minutes
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'javac Addition.java' // Compile Java program
            }
        }
        
        stage('Test') {
            steps {
                sh 'java Addition' // Run Java program
            }
        }
    }
}
