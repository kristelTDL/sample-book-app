pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Application is being built'
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Unit Tests are being executed'
            }
        }
        stage('Deploy to DEV environment') {
            steps {
                echo 'Application deploying to DEV environment'
            }
        }
        stage('Testing DEV environment') {
            steps {
                echo 'Application is being tested on DEV environment'
            }
        }
        stage('Deploy to STG environment') {
            steps {
                echo 'Application deploying to STG environment'
            }
        }
        stage('Testing STG environment') {
            steps {
                echo 'Application is being tested on STG environment'
            }
        }
        stage('Deploy to PRD environment') {
            steps {
                echo 'Application deploying to PRD environment'
            }
        }
        stage('Testing PRD environment') {
            steps {
                echo 'Application is being tested on PRD environment'
            }
        }
        
    }
}

/*
Build of application
Unit test execution
Build deployment in “DEV” environment
Test execution against DEV environment
Build deployment in “STG” environment
Test execution against STG environment
Build deployment in “PRD” environment
Test execution against PRD environment
*/