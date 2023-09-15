pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the application using Maven..."                
            }
        }
      
        stage('Test') {
            steps {
                echo "Running unit tests using Katalon Studio..."
                echo "Running integration tests using Katalon Studio..."
            }
            post {
                success {
                        mail to: "smthiri01@gmail.com",
                        subject: "Testing Success",
                        body: "The testings have ran successfully!"

                }
            }
        }
      
        stage('Code Analysis') {
            steps {
                echo 'Conducting code analysis using SonarQube...'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Conducting security scan using SonarQube...'
            }
            post {
                success {
                        mail to: "smthiri01@gmail.com",
                        subject: "Scan Success",
                        body: "The security scan has completed successfully!"

                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server AWS EC2...'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Conducting integration tests on staging...'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to production server AWS EC2..."
            }
        }
    }
}
