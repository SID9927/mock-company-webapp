pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // TODO: Build the project
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                // TODO: Run tests
                sh './gradlew test'
            }
        }
    }

    post {
        always {
            junit 'build/test-results/**/*.xml'
            archiveArtifacts artifacts: 'build/libs/*.jar', allowEmptyArchive: true
        }
    }
}
