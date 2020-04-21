pipeline {
    agent any

    tools {
        maven 'localMaven'
    }
    
    environment {
        PATH = '/usr/local/bin:$PATH'
    }

    stages {
        stage('Init') {
            steps {
                echo "path - ${PATH}"
            }
        }
        stage('Build') {
            steps {
                echo "CS - Building ..."
                sh "mvn clean package"
                echo "path - ${PATH}"
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
    
}