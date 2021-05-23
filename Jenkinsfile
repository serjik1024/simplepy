/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker rmi simplepy -f'
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
                sh 'docker run -p 5000:5000 -d --name=simplepy_instance simplepy'
            }
        }
    }
}
