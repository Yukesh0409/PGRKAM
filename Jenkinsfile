pipeline {
    agent any
    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout from Git') {
            steps {
                // Checkout the repository into a specific directory
                dir('.') {
                    git branch: 'main', url: 'https://github.com/sharanAlwar/PGRKAM.git'
                    sh "pwd"
                }
            }
        }

        stage('SSH Agent') {
            steps {
                sshagent(['big-docker-server']) {
                    sh "ssh -tt -o StrictHostKeyChecking=no ubuntu@18.207.144.22 ls"
                    sh "echo 'hello world' "
                    sh "ls"
                }
            }
        }
    }
}
