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
                sh "python3 -m pytest"
            }
        }
    }
    post {
        always {
            script {
                echo "Debug: baseUrl - ${baseUrl}, teamDomain - ${teamDomain}, channel - ${channel}, tokenCredentialId - ${tokenCredentialId}"

                slackSend channel: "#jenkins", message: "Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
            }
        }
    }
}
