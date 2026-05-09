pipeline{
    agent any

    stages{

        stage('Build'){
            steps{
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Build Docker Image'){
            steps{
                sh 'docker build -t jenkins-demo .'
            }
        }
    }
}