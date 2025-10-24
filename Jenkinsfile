pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('Unit Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Code Quality') {
            steps {
                // Run JaCoCo report generation
                bat 'mvn jacoco:report'
            }
            post {
                success {
                    // Archive JaCoCo HTML report so you can view it in Jenkins
                    archiveArtifacts artifacts: 'target/site/jacoco/**', fingerprint: true
                }
            }
        }
    }

    post {
        always {
            // Always publish test results (if using JUnit)
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
