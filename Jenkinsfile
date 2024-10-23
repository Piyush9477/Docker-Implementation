pipeline{
    agent any

    stages {
        stage('Clone Repository'){
            steps{
                git 'https://github.com/Piyush9477/Docker-Implementation.git'
            }
        }

        stage('Build Docker Image'){
            steps{
                sh 'docker build -t java-calculator-app .'
            }
        }

        stage('Run Docker Container'){
            steps{
                sh 'docker run -d -p 8080:8080 --name calculator-app java-calculator-app'
            }
        }

        stage('Post-build Cleanup'){
            steps{
                sh 'docker system prune -f'
            }
        }
    }

    post{
        always{
            echo 'Cleaning up workspace...'
            deleteDir()
        }
    }
}