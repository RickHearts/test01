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

    stage('Edge / Print Message ') {
      steps {
        echo 'edge'
      }
    }

    stage('sleep') {
      steps {
        sleep 4
      }
    }

    stage('') {
      steps {
        input(message: 'approve me ', ok: 'continue')
      }
    }

  }
}