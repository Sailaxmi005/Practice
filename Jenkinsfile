pipeline {
    agent any
    environment {
      JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-amd64"
    }
    stages {
        stage("Checkout Code from git") {
            steps {
                script {
                    git 'https://github.com/Sailaxmi005/Practice.git'
                }
            }
        }
        stage("Build code using Maven") {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }
        stage("execute ls to check files") {
            steps {
                script {
                    sh 'ls -la'
                }
            }
        }
        stage("Archive file locally on Jenkins") {
            steps {
                archiveArtifacts 'target/*'
            }
        }
        stage("clean workspace") {
            steps {
                cleanWs()
            }
        }
    }
}
