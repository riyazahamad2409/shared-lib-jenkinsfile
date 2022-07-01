@Library('shared-library') _

def config = [ name: 'jenkins', dayOfWeek: 'Friday' ]
def args = [ repo: 'java-projects' ]

pipeline {
    agent any
    tools {
        maven 'Maven' 
    }
    environment {
        PROJECT_ID = 'mineral-hangar-354512'
        CLUSTER_NAME = 'cluster-1'
        LOCATION = 'us-central1-c'
        CREDENTIALS_ID = 'Kubernetes'
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
                buildJavaApp()
            }
        }
        stage('Build & Push image') {
            steps {
                buildDockerImage()
            }
        }
        stage('Deploy to GKE') {
            steps {
                deployImageGke()
            }
        }
    }
}
