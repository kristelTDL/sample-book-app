pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                scripts {
                    docker-build()
                }
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

// function for building the docker image
def docker-build() {
    echo 'Building Docker image...'
}
// function to optimize deployment

// function to optimize api testing