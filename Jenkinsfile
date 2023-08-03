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
                sh "python3 main.py"
            }
        }
        stage('Test') {
            steps {
                sh "cd tests"
                sh "python3 test_func.py"
            }
        }
    }
}
