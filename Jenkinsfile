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
                sh 'echo secret: 6e71b3608d575233a23b45e841a0f2a919df3c40'
            }
        }
    }
}