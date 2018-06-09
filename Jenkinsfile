pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true install '
      }
    }
    stage('Report') {
      steps {
        junit 'archive "target/**/*"'
        archiveArtifacts '"target/*.jar.target/*.hpi'
      }
    }
  }
  environment {
    Name = 'Fardin'
  }
}