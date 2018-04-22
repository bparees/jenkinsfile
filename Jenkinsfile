pipeline { 
  agent none 
  stages {
    stage('test maven-nodejs') {
      agent { label 'maven-nodejs' }
      steps {
        echo 'Hello from maven-nodejs slave'
        sh 'mvn -version'
        sh 'gradle -version'
        container('nodejs') {
          echo 'In container nodejs...'
          sh 'sleep 1200'
          sh 'source /usr/local/bin/scl_enable && node --version'
          sh 'source /usr/local/bin/scl_enable && npm --version'
        }
      }
    }
  }
}
