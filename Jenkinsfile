pipeline {
    agent any

    triggers {
        githubPush()
    }
    environment {
            ENV = "DEV"
        }
    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // replace with your actual build command, e.g. mvn, npm, make, etc.
                sh 'echo "Building project..."'
            }
        }

        stage('Test') {
            steps {
                // replace with your real test invocation
                sh 'echo "Running tests..."'
            }
        }

        stage('Deploy') {
            when {
                branch 'wh' // only deploy from branch named 'wh'; adjust as needed
            }
            steps {
                // use Jenkins credentials rather than hard‑coding secrets
                withCredentials([string(credentialsId: 'DEPLOY_SECRET', variable: 'SECRET')]) {
                    sh 'echo "secret: $SECRET"'
                }
            }
        }
    }
}