pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'pip3 install -r requirements.txt || echo "No requirements file found"'
            }
        }

        stage('Run Script') {
            steps {
                echo 'Running Python script...'
                sh 'python3 script.py'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
    }
}
