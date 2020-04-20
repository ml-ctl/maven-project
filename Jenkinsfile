pipeline {
    agent any

    tools {
        maven 'localMaven'
    }
    
    stages {
        stage('Init') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
                sh 'docker build . -t tomcatwebapp:${env.BUILD_ID}'
            }
        }
    }
    
}