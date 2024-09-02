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
        emailext (
            subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
            body: "Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' was successful. Please find the logs attached.",
            to: 'shishirgenz@gmail.com',
            attachLog: true,
            attachmentsPattern: "**/build.log"
        )
    }
    failure {
        emailext (
            subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
            body: "Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed. Please find the logs attached.",
            to: 'shishirgenz@gmail.com',
            attachLog: true,
            attachmentsPattern: "**/build.log"
        )
    }
}
}