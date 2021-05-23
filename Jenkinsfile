/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'sudo -sH docker build . -t simpleapp'
            }
        }
        stage('Unit test') {
            steps {
                sh 'sudo -sH docker run simplepy pytest -v'
            }
        }

        stage('Run app') {
            steps {
                sh 'sudo -sH docker run simplepy'
            }
        }
    }
}
