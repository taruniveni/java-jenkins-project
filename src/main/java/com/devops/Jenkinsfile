pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Show Target') {
            steps {
                sh 'ls -lh target/'
            }
        }

        stage('Show JAR') {
            steps {
                sh 'ls -lh target/*.jar'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/devops-java-app-1.0.jar'
            }
        }
    }
}
