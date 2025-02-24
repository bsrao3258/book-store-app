@Library('book-store-shared-library') _

pipeline {
    agent any

    environment {
        APP_NAME = 'BookStoreApp'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/bsrao3258/book-store-app.git', credentialsId: 'ssh private'
            }
        }
        stage('Build') {
            steps {
                script {
                    buildApp(APP_NAME)
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    testApp(APP_NAME)
                }
            }
        }

        stage('Deploy to Dev') {
            steps {
                script {
                    deployApp(APP_NAME, 'dev')
                }
            }
        }

        stage('Deploy to Test') {
            steps {
                script {
                    deployApp(APP_NAME, 'test')
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                script {
                    deployApp(APP_NAME, 'staging')
                }
            }
        }

        stage('Deploy to Prod') {
            steps {
                script {
                    deployApp(APP_NAME, 'prod')
                }
            }
        }
    }
}
