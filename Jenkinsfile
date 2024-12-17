pipeline {
    agent {
            docker {
                image 'node:slim'
            }
    }

    stages {
        stage('Hello') {
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
            steps {
                sh 'npm run test'
            }
        }
    }
}
