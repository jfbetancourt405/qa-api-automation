pipeline {
    agent any

    stages {

        stage('Run API Tests') {
            steps {
                bat '''
                npx -y newman run tests\\collections\\users-api-tests.json ^
                -r cli
                '''
            }
        }

    }
}