pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'pytest'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage completed'
            }
        }

        stage('Deploy') {
            steps {
                bat 'python app.py'
            }
        }
    }

    post {
        failure {
            echo 'Build Failed!'
        }
        success {
            echo 'CI/CD Pipeline executed successfully!'
        }
    }
}