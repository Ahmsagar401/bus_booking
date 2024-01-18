pipeline {
  agent { label 'slave1' }
  stages {
    stage('checkout') {
      steps {
        sh 'rm -rf bus_booking'
        sh 'git clone https://github.com/Ahmsagar401/bus_booking.git'
      }
    }
    stage('build') {
      steps {
        sh 'mvn --version'
        sh 'mvn clean install'
      }
    }
    stage('run JAR locally') {
      steps {
        // Run the JAR file using java -jar
        sh 'nohup timeout 10s java -jar /home/slave1/workspace/Bus_booking_develop/target/bus-booking-app-1.0-SNAPSHOT.jar > output.log 2>&1 &"
        // Sleep for a while to allow the application to start
        sleep 30
      }
    }
    stage('deploy') {
      steps {
        sh 'ssh root@172.31.28.235
        sh 'scp /home/slave1/workspace/Bus_booking_develop/target/bus-booking-app-1.0-SNAPSHOT.jar root@172.31.28.235:/opt/apache-tomcat-8.5.98/webapps/'
      }
    }
  }
}

    
