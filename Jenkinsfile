pipeline {
    agent any
    environment {
        JAVA_HOME = "/usr/lib/jvm/java-8-openjdk-amd64"
    }
    stages {
        stage('checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/steventongsf/multitier-webstack'
            }
        }
        stage('build') {
            steps {
                dir("app") {
                    sh "mvn install -e"
                }
            }
        }
        stage('test') {
            steps {
                dir("app") {
                    sh "mvn test -e"
                }
            }
        }
    }
}