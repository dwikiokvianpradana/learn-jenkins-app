pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('NPM command') {
            agent {
                docker {
                    image 'node:slim'
                }
            }
            steps {
                sh 'npm --version'
            }
        }
    }
}
