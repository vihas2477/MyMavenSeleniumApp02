pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/vihas2477/MyMavenSeleniumApp01.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -l target/'
            }
        }

        stage('Run') {
            steps {
                sh 'java -jar target/app.jar'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: Build and execution completed'
        }
        failure {
            echo 'FAILED: Check logs'
        }
    }
}
