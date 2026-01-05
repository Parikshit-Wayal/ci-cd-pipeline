pipeline {
    agent any

    tools {
        sonarQube 'SonarScanner'
    }

    environment {
        SONARQUBE_SERVER = 'SonarQube'
        SONAR_PROJECT_KEY = 'nodejs_App'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv("${SONARQUBE_SERVER}") {
                    sh """
                        sonar-scanner \
                        -Dsonar.projectKey=${SONAR_PROJECT_KEY} \
                        -Dsonar.sources=. \
                        -Dsonar.language=js
                    """
                }
            }
        }

        stage('Quality Gate Enforcement') {
            steps {
                timeout(time: 5, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}

