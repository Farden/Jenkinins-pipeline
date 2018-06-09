pipeline {
  agent any
  stages {
    stage('Initialize ') {
      steps {
        sh '''echo PATH = ${PATH}
Echo M2_HOME = ${M2_HOME}
mvn clean'''
      }
    }
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