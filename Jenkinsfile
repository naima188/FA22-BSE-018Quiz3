pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out Java branch...'
                checkout scm
            }
        }
        
        stage('Build Java') {
            steps {
                echo 'Compiling Java program...'
                bat 'javac HelloJava.java'
            }
        }
        
        stage('Run Java') {
            steps {
                echo 'Executing Java program...'
                bat 'java HelloJava'
            }
        }
        
        stage('Cleanup') {
            steps {
                echo 'Cleaning up...'
                bat 'del HelloJava.class'
            }
        }
    }
    
    post {
        success {
            echo 'Java pipeline executed successfully!'
        }
        failure {
            echo 'Java pipeline failed!'
        }
    }
}
