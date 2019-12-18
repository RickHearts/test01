pipeline {
  agent any
  stages {
    stage('Chrome') {
      parallel {
        stage('Chrome') {
          steps {
            echo 'Chrome Tests'
          }
        }

        stage('Firefox') {
          steps {
            echo 'Firefox Tests'
          }
        }

      }
    }

  }
}