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
                git branch: 'main', url: 'https://github.com/sharanAlwar/PGRKAM.git'
            }
        }

        stage('Testing') {
            steps {
                echo "This is the testing phase"
            }
        }
        
        stage('SSH Remote Command') {
            steps {
                script {
                    echo "hello world"
                    // Define the credentials ID for SSH
                    def SSH_CREDENTIALS = credentials('big-docker-server')
                    // Use the SSH key to execute commands on the remote server
                    sshagent(credentials: [SSH_CREDENTIALS]) {
                        sh "ssh ubuntu@ip-172-31-27-160 'echo hello >> hello.txt'"
                    }
                }
            }
        }
    }
}
