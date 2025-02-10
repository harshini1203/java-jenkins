pipeline {
    agent any

    environment {
        JAVA_HOME = tool 'jdk-17'  // Ensure Jenkins has JDK configured
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/harshini1203/java-jenkins.git'
            }
        }

        stage('Compile Java Program') {
            steps {
                script {
                    sh 'javac TimestampPrinter.java'
                }
            }
        }

        stage('Run Java Program') {
            steps {
                script {
                    sh 'java TimestampPrinter'
                }
            }
        }
    }

    post {
        success {
            echo 'Build successful! Timestamp printed.'
        }
        failure {
            echo 'Build failed! Check errors.'
        }
    }
}
