#!groovy

pipeline {
	agent {
		label { label 'mavenjava'}
	}
  stages {
  	stage('Maven Install') {
    	agent {
      	     label { label 'mavenjava'}
		{
        	image 'maven:3.5.0'
        }
      }
      steps {
      	sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t shanem/spring-petclinic:latest .'
      }
    }
  }
}
