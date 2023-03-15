
pipeline {
    agent {
        label { label 'ecsAgent'}
    }
     
    stages {	 
        stage('docker') {
            steps {		
                image 'maven:3.9.0-eclipse-temurin-11' 
                args '-v /root/.m2:/root/.m2' 
            }
         }
    }
	
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
