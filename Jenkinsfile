pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-repo/java-app.git'
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
        stage('Deploy') {
            steps {
                sh 'scp -i /path/to/your-key.pem target/*.war ubuntu@<tomcat-ec2-ip>:/opt/tomcat9/webapps/'
            }
        }
    }
}
