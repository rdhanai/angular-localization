pipeline {
  agent any
  stages {
    stage('Install') {
      steps { 'npm install' }
    }
    stage('Test') {
      parallel {
        stage('Static code analysis') {
            steps {  'npm run lint' }
        }
        stage('Unit tests') {
            steps {  'npm run test' }
        }
      }
    }
    stage('Build') {
      steps { 'npm run build' }
    }
  }
}
