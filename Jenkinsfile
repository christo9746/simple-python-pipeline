pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Setup Environment') {
            steps {
                echo 'Setting up Python environment...'
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Script') {
            steps {
                echo 'Running Python script...'
                sh 'python3 script.py'
            }
        }

        stage('Post-Cleanup') {
            steps {
                echo 'Cleaning up...'
                sh 'rm -rf venv'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
    }
}
