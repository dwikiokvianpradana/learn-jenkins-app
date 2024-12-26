pipeline {
    agent any

    stages {
        stage('Install Dependency') {
            agent {
                docker {
                    image 'node:slim'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    npm ci
                '''
            }
        }
        stage('Build') {
            agent {
                docker {
                    image 'node:slim'
                    reuseNode true
                }
            }
            steps {
                sh '''
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
