pipeline {
    agent {
        docker {
            image 'maven:3.8.3-openjdk-11-slim'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    environment {
        MAVEN_OPTS = '-Dmaven.repo.local=.m2/repository'
        JAVA_HOME = '/usr/local/openjdk-11'
        PATH = "/usr/local/openjdk-11/bin:${PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
