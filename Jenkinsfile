@Library('shared-library') _

def config = [ name: 'jenkins', dayOfWeek: 'Friday' ]
def args = [ repo: 'java-projects' ]

pipeline {
    agent any
    
    
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
        stage('Build') {
            steps {
                buildJavaApp()
            }
        }
    }
}
