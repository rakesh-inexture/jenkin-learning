pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/shubhamsinha1010/jenkin-learning.git']])
            }
        }
        stage('Build') {
            steps {
                sh "pip install -r requirements.txt"
                sh "cd content"
                sh "python3 content/main.py"
            }
        }
        stage('Test') {
            steps {
                sh "cd tests"
                sh "python3 tests/test_func.py"
            }
        }
    }
}
