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

        stage('Deploy Container'){
             steps{
                 sh 'docker stop springboot-container || true'
                 sh 'docker rm springboot-container || true'
                 sh 'docker run -d -p 8081:8081 --name springboot-container jenkins-demo'
             }
        }


    }
}