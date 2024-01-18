pipeline{
  agent { label 'java' }
  stages {
    stage ( 'checkout' ) {
      steps {
        sh 'rm -rf weather-update'
        sh 'git clone https://github.com/Nethravathi-R/weather-update.git'
      }
   }
    stage ( 'build' ) {
      steps {
        sh 'mvn --version'
        sh 'mvn clean install'        
        }      
    }
    stage ( 'Run Locally' ) {
      steps {
        script {
          sh 'java -jar /home/slave1/workspace/WeatherUpdate/target/weather-forecast-app-1.0-SNAPSHOT.jar &'
          sleep 20
        
        }
      }
   }
    stage ( 'Deploy' ) {
      steps {
        sh 'ssh root@172.31.41.184'
        sh 'scp /home/slave1/workspace/WeatherUpdate/target/weather-forecast-app-1.0-SNAPSHOT.jar root@172.31.41.184:/opt/apache-tomcat-8.5.98/webapps'
      }
     }    
    }
  }
