pipeline {
  agent any
  triggers {
    githubPush()
  }
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
    stage('Build Docker') {
      steps {
        script {
          docker.build("preethamreddydev/node-ci-demo:${env.BUILD_NUMBER}")
        }
      }
    }
  }
}
