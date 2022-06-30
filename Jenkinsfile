@Library('shared-library') _

def config = [ name: 'jenkins', dayOfWeek: 'Friday' ]
def args = [ repo: 'java-projects' ]

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
        stage('Build image') {
            steps {
                buildDockerImage()
            }
        }
        stage('Push image') {
            steps {
                publishDockerImage()
            }
        }
    }
}
