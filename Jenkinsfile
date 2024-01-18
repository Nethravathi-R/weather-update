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
          sh 'java -jar "/home/slave1/workspace/WeatherUpdate/target/weather-forecast-app-1.0-SNAPSHOT.jar &"'
          sleep 20
        
        }
      }
   }
    
    }
  }
