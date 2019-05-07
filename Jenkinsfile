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
          echo '2nd step'
        }
      }
      stage('Three') {
        when {
          not {
            branch "master"
          }
        }
        steps {
          echo "Hello...!!!"
        }
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
