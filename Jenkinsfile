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
                echo "Code is built automatically through Gradle"
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Test is automatically done by JUnit"
            }
            post {
                success {
                    mail(
                        to: 'but05051@gmail.com',
                        subject: 'Build Status Email',
                        body: 'Build was successful'
                    )
                }
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
                echo "Quality check for code is done by Coverity"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Scan the code for detecting vulnerabilities using Checkmarx"
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        body: "This is the email test body",
                        subject: 'This is the test',
                        to: 'but05051@gmail.com'
                    )
                }
            }
        }
        stage('Integration tests on staging') {
            steps {
                echo "Integration tests are run on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying code to ${PRODUCTION_ENVIRONMENT} environment"
            }
        }
    }
}
