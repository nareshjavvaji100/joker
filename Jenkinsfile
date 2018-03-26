pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        catchError() {
          bat 'build'
        }
        
      }
    }
    stage('build') {
      steps {
        build(job: 'flipcart', propagate: true, quietPeriod: 2)
      }
    }
    stage('compile') {
      parallel {
        stage('compile') {
          steps {
            echo 'good work'
          }
        }
        stage('test') {
          steps {
            catchError()
          }
        }
      }
    }
  }
}