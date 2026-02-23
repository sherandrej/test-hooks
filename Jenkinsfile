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
                sh 'step Build'
            }
        }

        stage('Test') {
            steps {
                sh 'step Test'
            }
        }

        stage('Deploy') {
            when {
                branch 'wh'
            }
            steps {
                sh 'step Deploy'
            }
        }
    }
}