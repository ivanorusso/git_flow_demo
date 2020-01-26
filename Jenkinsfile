@Library('shared_lib_example_1') _

pipeline 
{
    agent none
    stages 
    {
        stage('Test') 
        {
            parallel 
            {
                stage('Test On docker') 
                {
                    agent { docker { image 'node:7-alpine' } }
                    steps {
                        sh 'node --version'
                    }
                }
                stage('Test On dev7') 
                {
                    agent any
                    steps {
                        buildJavascriptApp deploy: false, {
                            notify type: "slack", message: "Build succeeded"
                        }  
                    }
                }
            }
        }
    }
}
   
