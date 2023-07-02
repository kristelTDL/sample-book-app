pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                script {
                    buildDockerImage()
                }
            }
        }
        stage('unit-tests') {
            steps {
                script {
                    executeUnitTests()
                }
            }
        }
        stage('deploy-dev') {
            steps {
                script {
                    deploy("DEV")
                }
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                script {
                    executeAPITests("DEV")
                }
            }
        }
        stage('deploy-stg') {
            steps {
                script {
                    deploy("STG")
                }
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                script {
                    executeAPITests("STG")
                }
            }
        }
        stage('deploy-prd') {
            steps {
                script {
                    deploy("PRD")
                }
            }
        }
        stage('api-integration-tests-prd') {
            steps {
                script {
                    executeAPITests("PRD")
                }
            }
        }
       
        
    }
}

// function for building the docker image
def buildDockerImage() {
    echo "Building Docker image..."
}

// function for unit tests
def executeUnitTests() {
    echo "Running unit tests for node application in Docker container..."
}

// function to optimize deployment
def deploy(String env) {
    echo "Deployment triggered on ${env} environment..."
}

// function to optimize api testing
def executeAPITests(String env) {
    echo "API integration tests triggered on ${env} environment"
}