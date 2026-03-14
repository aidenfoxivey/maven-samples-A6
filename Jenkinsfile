pipeline {
  agent any
  tools {
      maven 'DHT_MVN'
      jdk 'DHT_SENSE'
  }
  stages {
    stage('Bisect') {
      steps {
        sh 'git bisect start'
        sh 'git bisect bad HEAD'
        sh 'git bisect good 34d3197'
        sh 'git bisect run mvn test'
        sh 'git bisect reset'
      }
    }
  }
}
