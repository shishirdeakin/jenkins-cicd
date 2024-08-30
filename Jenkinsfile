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
                echo 'Deploying to staging server with AWS EC2 Instance'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging with Selenium...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server with AWS EC2 Instance'
            }
        }
    }
    post {
    success {
        emailext to: 'shishirgenz@gmail.com',
                subject: "SUCCESS: ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: "The pipeline has successfully passed the ${currentBuild.currentResult} stage."
    }
    failure {
        emailext to: 'shishirgenz@gmail.com',
                subject: "FAILURE: ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: "The pipeline has failed at the ${currentBuild.currentResult} stage.",
                attachLog: true
    }
}
}