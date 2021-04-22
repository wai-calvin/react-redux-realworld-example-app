pipeline {
//   environment {
//     registry = "cwai96/realworld_frontend"
//     registryCredential = 'dockerhub'
//     dockerImage = ''
//   }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/wai-calvin/react-redux-realworld-example-app.git'
      }
    }
    stage('Build Frontend') {
        steps {
            sh "docker build -t cwai96/realworld_frontend:$BUILD_NUMBER ."
        }
    }
    // stage('Building image') {
    //   steps{
    //     script {
    //       dockerImage = docker.build registry + ":$BUILD_NUMBER"
    //     }
    //   }
    // }
    // stage('Deploy Image') {
    //   steps{
    //     script {
    //       docker.withRegistry( '', registryCredential ) {
    //         dockerImage.push()
    //       }
    //     }
    //   }
    // }
  }
}