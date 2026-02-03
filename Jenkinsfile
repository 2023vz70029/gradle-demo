pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pulls the code from the Git repository defined in the job
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                // Runs the Gradle test task which also compiles the code
                // Use './gradlew' for Linux/macOS Jenkins nodes
                sh './gradlew clean test'
            }
        }

        stage('Archive Artifact') {
            steps {
                // Task 2.4: Saves the JAR file so it appears on the Jenkins dashboard
                // The JAR is typically found in build/libs/
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    }
}
