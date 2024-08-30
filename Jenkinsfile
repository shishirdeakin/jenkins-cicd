pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests with JUnit'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis with SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP Check...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging with Selenium...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
            }
        }
    }
    post {
    success {
        emailext to: 's224365862@deakin.edu.au',
                subject: "SUCCESS: ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: "The pipeline has successfully passed the ${currentBuild.currentResult} stage."
    }
    failure {
        emailext to: 's224365862@deakin.edu.au',
                subject: "FAILURE: ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: "The pipeline has failed at the ${currentBuild.currentResult} stage.",
                attachLog: true
    }
}
}