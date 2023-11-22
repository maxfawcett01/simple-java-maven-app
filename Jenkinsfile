pipeline {
    agent {
        docker {
            image 'maven:3.9.5-eclipse-temurin-17-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Checkout') {
            steps {
                dir('C:/Users/maxfa/OneDrive/Documents/GitHub/simple-java-maven-app') {
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    def mavenHome = tool 'Maven'
                    def mavenCMD = "${mavenHome}/bin/mvn"

                    bat "${mavenCMD} -B -DskipTests clean package"
                }
            }
        }
    }
}