pipeline {
  agent any
  stages {
    stage('dev code pull') {
      steps {
        echo 'dev build'
      }
    }

    stage('Deploy to QA') {
      steps {
        echo 'Deploy to QA'
      }
    }

    stage('UI smoke tests') {
      parallel {
        stage('UI smoke tests') {
          steps {
            echo 'UI Tests'
          }
        }

        stage('API tests') {
          steps {
            echo 'This will run API tests'
          }
        }

        stage('Performance test') {
          steps {
            echo 'This will run performance test'
          }
        }

        stage('error') {
          steps {
            echo 'This will run performance test'
          }
        }

      }
    }

    stage('QA approval') {
      steps {
        echo 'QA approval needed'
      }
    }

    stage('UAT deploy') {
      steps {
        echo 'Deploy to UAT'
      }
    }

    stage('UAT certificates') {
      steps {
        echo 'manual approval'
        input 'QA approval needed..'
      }
    }

    stage('Prod deploy') {
      steps {
        echo 'This will deploy to prod'
        when() {
          branch 'master'
        }

      }
    }

  }
}