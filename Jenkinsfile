@Library('shared-library') _

def config = [ name: 'jenkins', dayOfWeek: 'Friday' ]
def args = [ repo: 'Angular-HelloWorld' ]
def file = [ name: 'deployment' ]
pipeline {
    agent any
    tools {
        nodejs 'NodeJS' 
    }
    
    environment {
        PROJECT_ID = 'mineral-hangar-354512'
        CLUSTER_NAME = 'cluster-1'
        LOCATION = 'us-central1-c'
        CREDENTIALS_ID = 'Kubernetes'
        DEPLOYMENT_YAML = 'deployment.yaml'
    }
    
    stages {

        stage('Example') {
            steps {
                helloWorld(config)
            }
        }
    
        stage('scm checkout') { 
            steps {   
                gitCheckout(args)
            }
        }
        stage('Build app') {
            steps {
                buildAngularApp()
            }
        }
        
    }
}
