pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }
        stage('Run Script') {
            steps {
                echo 'Executing Python script...'
                sh '''
                    python3 script.py
                '''
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution completed!'
        }
    }
}
