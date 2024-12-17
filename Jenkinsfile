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
                sh 'ls -la'
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
