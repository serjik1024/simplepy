/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build . -t simplepy'
            }
        }
        stage('Unit test') {
            steps {
                sh 'docker run simplepy pytest -v'
            }
        }

        stage('Run app') {
            steps {
                sh 'docker run simplepy'
            }
        }
    }
}
