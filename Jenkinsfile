pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn clean compile'
        }
        
      }
    }
    stage('Test') {
      parallel {
        stage('UnitTest') {
          steps {
            withMaven(maven: 'M3') {
              sh 'mvn -Dmaven.test.failure.ignore test'
            }
            
          }
        }
        stage('IntegrationTest') {
          steps {
            echo 'testing integration...'
          }
        }
      }
    }
    stage('Package') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn -Dmaven.test.skip=true verify'
        }
        
      }
    }
  }
}