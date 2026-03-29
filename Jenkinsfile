pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'npm install -g newman'
                bat 'npm install -g newman-reporter-htmlextra'
            }
        }

        stage('Run API Tests') {
            steps {
                bat '''
                npx newman run tests\\collections\\users-api-tests.json ^
                -r cli,htmlextra ^
                --reporter-htmlextra-export reports\\api-report.html
                '''
            }
        }

    }

    post {
        always {
            archiveArtifacts artifacts: 'reports/*.html', fingerprint: true
        }
    }
}
