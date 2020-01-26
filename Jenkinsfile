@Library('shared_lib_example_1') _

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
    }
    
    agent any
    
    stages {
        stage('Test2'){
            steps {
                buildJavascriptApp deploy: false, {
                    notify type: "slack", message: "Build succeeded"
                }  
            }
        }
    }
}
