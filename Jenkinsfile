pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add actual build commands here
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add actual test commands here
            }
        }
    }
    post {
        success {
            emailext (
                subject: 'Build Successful: ${JOB_NAME} [${BUILD_NUMBER}]',
                body: 'Good news! The build was successful.\n\nJob: ${JOB_NAME}\nBuild Number: ${BUILD_NUMBER}\n\nCheck it out here: ${BUILD_URL}',
                to: 'aishbirajdar2306@gmail.com'
            )
        }
        failure {
            emailext (
                subject: 'Build Failed: ${JOB_NAME} [${BUILD_NUMBER}]',
                body: 'Unfortunately, the build failed.\n\nJob: ${JOB_NAME}\nBuild Number: ${BUILD_NUMBER}\n\nPlease review the build logs: ${BUILD_URL}',
                to: 'aishbirajdar2306@gmail.com'
            )
        }
    }
}
