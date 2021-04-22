pipeline {
  environment {
    registry = "cwai96/realworld_frontend"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/wai-calvin/react-redux-realworld-example-app.git'
      }
    }
    stage('Build Frontend') {
        steps {
            sh "docker build -t cwai96/realworld_frontend:v1.0.$BUILD_NUMBER ."
        }
    }
  }
}

