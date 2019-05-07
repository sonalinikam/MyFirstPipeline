pipeline {
  agent any
    stages {
      stage('One') {
        steps {
          echo 'This is Sonali Nikam...!!!'
        }
      }
      stage('Two') {
        steps {
          input('Do you want to proceed?')
        }
      }
      stage('Three') {
        steps {
          when {
            not {
              branch "master"
            }
          }
          echo 'Hello'
        }
        stage('Four') {
          parallel {
            stage('Unit Test') {
              steps {
                echo "Running Unit tests..."
              }
            }
            stage('Integration Test') {
              steps {
                agent {
                  docker {
                    reuseNode false
                    image 'ubuntu'
                  }
                }
                echo "Running Intergration tests..."
              }
            }
          }
        }
      }
    }
}
