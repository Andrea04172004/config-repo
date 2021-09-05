pipeline {
    environment {
    registry = "andrewkachmar/adetails"
    registryCredential = "dockerhub"
  }
    agent any
    tools {
        maven 'Maven 3.3.9'
        jdk 'openJDK9'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                //sh 'mvn clean package'
                sh 'mvn clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}

