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
        sh 'mvn clean compile'
      }
    }
  }
}