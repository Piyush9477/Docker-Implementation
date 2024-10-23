pipeline{
    agent any

    stages {
        stage('Clone Repository'){
            steps{
                git 'https://github.com/Piyush9477/Docker-Implementation.git'
            }
        }

        stage('Build'){
            steps{
                sh 'javac sample.java'
            }
        }

        stage('Run'){
            steps{
                sh 'java sample'
            }
        }

        stage('Dockerize'){
            steps{
                sh 'docker build -t java-calculator-app .'
            }
        }   
    }

    post{
        success {
            echo 'Job completed successfully!'
        }
        failure {
            echo 'Job failed!'
        }
    }
}