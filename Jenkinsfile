pipeline {
    agent any

    tools {
        maven 'Maven 3.8.1'  // Optional: only if you’ve set up a Maven tool in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/hshreya1310/MavenApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/MavenApp-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo 'Build Success'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
