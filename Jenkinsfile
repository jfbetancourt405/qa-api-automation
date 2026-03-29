pipeline {
    agent any

    stages {

        stage('Install Newman') {
            steps {
                bat 'npm install -g newman'
            }
        }

        stage('Run API Tests') {
            steps {
                bat 'newman run tests\\collections\\users-api-tests.json'
            }
        }

    }
}