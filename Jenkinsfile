pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Suhas8349/saucedemo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Login Test') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass=com.example.App'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Success!'
        }

        failure {
            echo 'Pipeline Failed!'
        }
    }
}
