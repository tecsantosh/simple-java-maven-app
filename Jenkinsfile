pipeline {
    agent {
        label { label 'ecsAgent'}
    }
     
    environment {
        DOCKER_IMAGE = 'maven:3.9.0-eclipse-temurin-11'
        MAVEN_CMD = 'mvn -B -DskipTests clean package'
    }

    stages {
        stage('docker') {
            steps {		
                container(name: 'maven', image: DOCKER_IMAGE) {
                    // no need to mount the Maven config directory since the Docker image should contain it
                }
            }
        }

        stage('Build') { 
            steps {
                container(name: 'maven', image: DOCKER_IMAGE) {
                    sh MAVEN_CMD
                }
            }
        }
    }
}
