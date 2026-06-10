pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "soc-app"
        CONTAINER_NAME = "soc-container"
        PATH = "C:\\Users\\agrls\\anaconda3;C:\\Users\\agrls\\anaconda3\\Scripts;${env.PATH}"
    }

    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        stage('Dependency Audit (SCA)') {
            steps {
                script {
                    echo 'Running pip-audit for third-party vulnerabilities on Windows...'
                    bat 'pip install pip-audit'
                    bat 'pip-audit -r app/requirements.txt'
                }
            }
        }

        stage('Static Analysis (SAST)') {
            steps {
                script {
                    echo 'Running Bandit security analysis on Windows...'
                    bat 'pip install bandit'
                    bat 'bandit -r app/ -ll'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    echo 'Building secure non-root Docker image...'
                    bat 'docker build -t "%DOCKER_IMAGE%" .'
                }
            }
        }

        stage('Stop Old Container') {
            steps {
                script {
                    echo 'Removing old running application instances...'
                    bat 'docker rm -f "%CONTAINER_NAME%" || exit 0'
                }
            }
        }

        stage('Deploy New Container') {
            steps {
                script {
                    echo 'Running container with logs volume mount...'
                    // %CD% is the absolute path to the current working directory in Windows Command Prompt
                    bat 'docker run -d -p 5000:5000 -v "%CD%/logs:/app/logs" --name "%CONTAINER_NAME%" "%DOCKER_IMAGE%"'
                }
            }
        }
    }
}