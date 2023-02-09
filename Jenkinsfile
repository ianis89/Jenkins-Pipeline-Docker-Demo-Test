pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ianis89/Jenkins-Pipeline-Docker-Demo-Test.git']])
            }
        }
        stage('Build') {
            steps {
                git branch: 'master', url: 'https://github.com/ianis89/Jenkins-Pipeline-Docker-Demo-Test.git'
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
    }
}