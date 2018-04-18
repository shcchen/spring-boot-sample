pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }
    stage('test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/*.xml', healthScaleFactor: 1)
      }
    }
    stage('package') {
      steps {
        sh 'mvn package'
        archiveArtifacts 'target/spring-boot-sample-data-rest-0.1.0.jar'
      }
    }
  }
}