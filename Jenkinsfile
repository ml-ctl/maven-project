pipeline {
    agent any

    tools {
        maven 'localMaven'
        docker 'localDocker'
    }
    
    stages {
        stage('Init') {
            steps {
                echo "CS - Initialization ..."
                echo "CS - Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "CS - Build number: ${env.BUILD_NUMBER}"
            }
        }
        stage('Build') {
            steps {
                echo 'CS - Building ...'
                sh 'mvn clean package'
                echo "CS - Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
    
}