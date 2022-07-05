@Library('shared-library') _

def config = [ name: 'jenkins', dayOfWeek: 'Friday' ]
def args = [ repo: 'java-projects' ]
def file = [ name: 'deployment', zone: 'us-central1-c', project: 'mineral-hangar-354512' ]

pipeline {
    agent any
    tools {
        maven 'Maven' 
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
                connectToGke(file)
            }
        }
    }
}
