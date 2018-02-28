pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/lehmannk/spring-petclinic.git'
      }
    }
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn clean compile'
        }
        
      }
    }
  }
}