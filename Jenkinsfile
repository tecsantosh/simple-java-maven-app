#!groovy

pipeline {
	agent {
		label { label 'mavenjava'}
	}
  stages {
  	stage('Maven Install') {
    	agent {
      	ecs {
        	image 'maven:3.5.0'
        }
      }
      steps {
      	sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
    	agent ecs
      steps {
      	sh 'docker build -t shanem/spring-petclinic:latest .'
      }
    }
  }
}
