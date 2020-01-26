pipeline {
    agent {
        docker { image 'node:7-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
        stage('Test2'){
            steps {
                buildJavascriptApp deploy: false, {
                    notify type: "slack", message: "Build succeeded"
                }
            }
        }
    }
}
