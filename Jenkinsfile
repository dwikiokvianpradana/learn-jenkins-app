pipeline {
    agent any

    stages {
        stage('NPM command') {
            agent {
                docker {
                    image 'node:slim'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    whoami
                    ls -la
                    npm --version
                    npm ci
                    npm run build
                '''
            }
        }
        stage('NPM test') {
            agent {
                docker {
                    image 'node:slim'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    whoami
                    ls -la
                    npm run test
                '''
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
