pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'C:\\Users\\but05\\OneDrive\\Project'  // Ensure backslashes are escaped
        TESTING_ENVIRONMENT = 'SIT753'
        PRODUCTION_ENVIRONMENT = 'Ella'
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from ${DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts"
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy the application to ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                script {
                    sleep time: 10, unit: 'SECONDS'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying code to ${PRODUCTION_ENVIRONMENT} environment"
            }
        }
    }
}
