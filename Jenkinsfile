pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage("build-docker-image") {
            steps {
                buildDockerImage()
            }
        }
        stage("deploy-dev") {
            steps {
                deploy("dev")
            }
        }
        stage("api-integration-tests-dev") {
            steps {
                executeAPITests("DEV")
            }
        }
        stage("deploy-stg") {
            steps {
                deploy("stg")
            }
        }
        stage("api-integration-tests-stg") {
            steps {
                executeAPITests("STG")
            }
        }
        stage("deploy-prd") {
            steps {
                deploy("prd")
            }
        }
        stage("api-integration-tests-prd") {
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
    sh "docker build --no-cache -t kristelj/sample-book-app ."
    // run unit tests in the image
    echo "Running unit tests for node application in Docker container..."
    //sh "docker pull kristelj/sample-book-app:latest"
    sh "docker run --rm --entrypoint=npm kristelj/sample-book-app run test"
    echo "Pushing Docker image to Docker Hub..."
    sh "docker push kristelj/sample-book-app"
}


// function to optimize deployment
def deploy(String env) {
    //git branch: 'main', poll: false, url 'https://github.com/kristelTDL/sample-book-app.git'
    echo "Deployment triggered on ${env} environment..."
    sh "docker-compose-v1 stop sample-book-app-${env}"
    sh "docker-compose-v1 rm sample-book-app-${env}"
    sh "docker-compose-v1 up -d sample-book-app-${env}"
}

// function to optimize api testing
def executeAPITests(String env) {
    echo "API integration tests triggered on ${env} environment"
    //git branch: 'main', poll: false, url: 'https://github.com/kristelTDL/course-js-api-framework.git'
    //sh "ls"
    //sh "docker run -v $WORKSPACE/test-reports/${env}:/api-test-automation/mochawesome-report/ --network=host --rm kristelj/api-tests run BOOKS BOOKS_${env}"
    // fetch api tests docker image

    // execute tests
}