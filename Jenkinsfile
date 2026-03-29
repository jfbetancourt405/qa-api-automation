pipeline {
    agent any

    stages {

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