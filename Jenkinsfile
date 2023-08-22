pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rakesh-inexture/jenkin-learning.git']])
            }
        }
        stage('Build') {
            steps {
                sh "pip install -r requirements.txt"
                
            }
        }
        stage('Test') {
            steps {
                sh "python3 -m pytest"
            }
        }
    }
}


