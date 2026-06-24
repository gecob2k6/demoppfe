pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Backend') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Frontend') {
            steps {
                sh 'cd demoppfe && npm install'
                sh 'cd demoppfe && ng build'
            }
        }

        stage('Unit Tests') {
            steps {
                sh 'mvn test'
            }
        }
    }
}