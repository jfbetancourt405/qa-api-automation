pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run API Tests') {
            steps {
                bat 'node_modules\\.bin\\newman run tests\\collections\\users-api-tests.json -r cli'
            }
        }

    }
}