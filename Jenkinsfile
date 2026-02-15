pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code...'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java program...'
                bat 'javac Hello.java'
            }
        }

        stage('Test Run') {
            steps {
                echo 'Running Java program...'
                bat 'java Hello'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: '*.class'
            echo 'CI Pipeline Successful ✅'
        }

        failure {
            echo 'CI Pipeline Failed ❌'
        }
    }
}
