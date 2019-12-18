pipeline {
  agent none
  stages {
    stage('Build & Test ') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore clean packag'
        stash(name: 'build-test-artifacts', includes: '**/target/surefire-reports/TEST-*.xml,target/*.jar')
      }
    }

    stage('Report & Publish') {
      parallel {
        stage('Report & Publish') {
          agent {
            node {
              label 'docker'
            }

          }
          steps {
            unstash 'build-test-artifacts'
            junit '**/target/surefire-reports/TEST-*.xml'
            archiveArtifacts 'onlyIfSuccessful: true, artifacts: \'target/*.jar'
          }
        }

        stage('Publishing') {
          agent {
            node {
              label 'docker'
            }

          }
          steps {
            echo 'wroking'
          }
        }

      }
    }

  }
}