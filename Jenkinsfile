pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/tabrez26-tech/springboot-cicd.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t springboot-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8082:8080 springboot-app'
            }
        }
    }
}
