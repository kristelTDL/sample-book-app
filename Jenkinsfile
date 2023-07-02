pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                buildDockerImage()
            }
        }
        stage('unit-tests') {
            steps {
                executeUnitTests()
            }
        }
        stage('deploy-dev') {
            steps {
                deploy("DEV")
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                executeAPITests("DEV")
            }
        }
        stage('deploy-stg') {
            steps {
                deploy("STG")
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                executeAPITests("STG")
            }
        }
        stage('deploy-prd') {
            steps {
                deploy("PRD")
            }
        }
        stage('api-integration-tests-prd') {
            steps {
                executeAPITests("PRD")
            }
        }
    }
}

// function for building the docker image
def buildDockerImage() {
    echo "Building Docker image..."
    // build docker image
    sh '--privileged docker build --no-cache -t kristelj/sample-book-app:latest .'
    // push image to Docker Hub
    sh 'docker push kristelj/sample-book-app:latest'
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