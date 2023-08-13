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
            }
        }
        stage('Test') {
            steps {
                sh "python3 -m pytest"
            }
        }
    }
    post {
        always {
            script {
                slackSend channel: "#jenkins", message: "Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
            }
        }
    }
}
