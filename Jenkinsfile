pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                scripts {
                    buildDockerImage()
                }
            }
        }
        stage('unit-tests') {
            steps {
                scripts {
                    executeUnitTests()
                }
            }
        }
        stage('deploy-dev') {
            steps {
                scripts {
                    deploy("DEV")
                }
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                scripts {
                    executeAPITests("DEV")
                }
            }
        }
        stage('deploy-stg') {
            steps {
                scripts {
                    deploy("STG")
                }
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                scripts {
                    executeAPITests("STG")
                }
            }
        }
        stage('deploy-prd') {
            steps {
                scripts {
                    deploy("PRD")
                }
            }
        }
        stage('api-integration-tests-prd') {
            steps {
                scripts {
                    executeAPITests("PRD")
                }
            }
        }
       
        
    }
}

// function for building the docker image
def buildDockerImage() {
    print "Building Docker image..."
}

// function for unit tests
def executeUnitTests() {
    print "Running unit tests for node application in Docker container..."
}

// function to optimize deployment
def deploy(String env) {
    print "Deployment triggered on ${env} environment..."
}

// function to optimize api testing
def executeAPITests(String env) {
    print "API integration tests triggered on ${env} environment"
}