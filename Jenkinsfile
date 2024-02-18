pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    IMAGE_NAME = 'maxkamov48/test'
    IMAGE_TAG = 'latest'
    APP_NAME = 'test'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}
