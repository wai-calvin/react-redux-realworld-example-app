pipeline {
  parameters {
        password(name: 'username', defaultValue: 'SECRET')
        password(name: 'password', defaultValue: 'SECRET')
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
    stage('Deploy to Docker Hub') {
        steps {
            sh 'docker login --username="${Username}" --password="${Password}"'
            sh "docker push cwai96/realworld_frontend:v1.0.$BUILD_NUMBER"
        }
    }
  }
}

