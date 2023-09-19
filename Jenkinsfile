@Library('library-test@main') _

pipeline {
    agent any
    stages{
        stage('checkout'){
            steps{
                helloWorld()
            }
        }
    }
    stage("Tools initialization") { 
        steps {
            sh "mvn --version"
            sh "java -version" 
        }
    }
    stage("Cleaning Workspace") {
        steps {
            sh "mvn clean"
        }
    }
    stage("Running Testcase") {
        sh "mvn test"
    }
    stage("Packaging Application") {
        steps {
            sh "mvn package -DskipTests"
        }
    }
}