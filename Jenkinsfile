@Library("ahmlibrary") _

pipeline {
  agent { label 'slave1' }
  stages {
    stage('checkout') {
      steps {
        sh 'git clone https://github.com/Ahmsagar401/bus_booking.git'
      }
    }
    stage('build') {
      steps {
        script {
          build 'install'
        }
      }
    }
  }
}
