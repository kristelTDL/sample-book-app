pipeline {
    agent any

    stages {
        stage('build-docker-image') {
            steps {
                echo 'Building Docker image...'
            }
        }
        stage('unit-tests') {
            steps {
                echo 'Running unit tests for node application in Docker container...'
            }
        }
        stage('deploy-dev') {
            steps {
                echo 'Deployment triggered on DEV environment...'
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                echo 'API integration tests triggered on DEV environment'
            }
        }
        stage('deploy-stg') {
            steps {
                echo 'Deployment triggered on STG environment...'
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                echo 'API integration tests triggered on STG environment'
            }
        }
        stage('deploy-prd') {
            steps {
                echo 'Deployment triggered on PRD environment...'
            }
        }
        stage('api-integration-tests-prd') {
            steps {
                echo 'API integration tests triggered on PRD environment'
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