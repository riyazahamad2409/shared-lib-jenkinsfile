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
                echo 'hello 2nd'
            }
        }
        stage('Build') {
            steps {
                buildJavaApp(args)
            }
        }
    }
}
