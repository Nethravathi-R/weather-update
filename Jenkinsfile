pipeline {
      agent { label 'java' }
     environment {
                   MAVEN_HOME = tool 'Maven'
                 }
  
      stages {
        stage ( 'checkout' ) {
          
          sh 'git clone https://github.com/Nethravathi-R/weather-update.git'          
        }

        stage ( 'build' ) {
          sh "mvn --version"
          sh "${MAVEN_HOME}/bin/mvn clean package"          
        }
        }
    }
