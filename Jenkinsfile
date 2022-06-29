@Library('shared-library') _

def config = [ name: 'jenkins', dayOfWeek: 'Friday' ]

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
                gitCheckout()
            }
        }
    }
}
