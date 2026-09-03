pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/LakshmiNarayanan-R0411/factorial-jenkins-dem.git'
            }
        }

        stage('Setup Environment') {
            steps {
                bat 'python --version'
            }
        }

        stage('Run Factorial Program') {
            steps {
                bat 'python factorial.py'
            }
        }

        stage('Archive Output') {
            steps {
                bat 'python factorial.py > output.txt'
                archiveArtifacts artifacts: 'output.txt', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}