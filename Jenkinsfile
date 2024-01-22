@Library("ahmlibrary") _

pipeline {
  agent { label 'slave1' }
  stages {
    stage('checkout') {
      steps {
        checkout()
      }
    }
    stage('build') {
      steps {
        sh 'mvn --version'
        sh 'mvn clean install'
      }
    }
  }
}
  
