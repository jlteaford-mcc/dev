CODE_CHANGES = getGitChanges()
pipeline {
    agent { docker { image 'python:3.5.1' } }
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('server-credentials')
    }
    stages {
        stage('build') {
            steps {
                echo 'building the application...'
                sh 'python --version'
                echo "building version ${NEW_VERSION}"
            }
        }
        stage('test') {
            steps {
                echo 'testing the application...'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying the application...'
                echo "deploying with ${SERVER_CREDENTIALS}"
                sh "${SERVER_CREDENTIALS}"
            }
        }
    }
}
