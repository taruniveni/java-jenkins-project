pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running application tests'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    mkdir -p deployed
                    cp target/devops-java-app-1.0.jar deployed/
                    echo "Application deployed successfully"
                '''
            }
        }

        stage('Verify') {
            steps {
                sh '''
                    ls -lh deployed/devops-java-app-1.0.jar
                    java -jar deployed/devops-java-app-1.0.jar
                '''
            }
        }
    }
}
