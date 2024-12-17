pipeline {
    agent any

    stages {
        stage('Hello') {
            agent {
                docker {
                    image 'node:slim'
                    reuseNode true
            }
        }
            steps {
                sh 'npm --version'
            }
        }
        stage('NPM command') {
            steps {
                sh 'npm run build'
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
                sh 'npm run test'
            }
        }
    }
}
