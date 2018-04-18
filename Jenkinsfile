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
  }
}