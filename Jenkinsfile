pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''pipeline {
    agent { any }
    stages {
        stage(\'build\') {
            steps {
                sh \'npm --version\'
            }
        }
    }
}'''
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