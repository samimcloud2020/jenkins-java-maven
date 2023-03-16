pipeline {
    agent {
        // Use a Maven agent to build the project
        maven {
            // Use JDK 11 to build the project
            jdk '8'
            // Use Maven version 3.8.2
            maven 'apache-maven-3.9.0'
            // Use a custom label for the agent
            label 'maven-agent'
            
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git repository
                git branch: 'main', url: 'https://github.com/samimcloud2020/jenkins-java-maven.git'
            }
        }

        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Run the tests using Maven
                sh 'mvn test'
            }
        }


        
    }
}
