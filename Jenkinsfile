pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build 1.0') {
          steps {
            sh 'echo some success build'
          }
        }

        stage('build 1.1') {
          steps {
            echo 'success build'
          }
        }

        stage('build 1.2') {
          steps {
            echo 'success'
          }
        }

      }
    }

    stage('build 2') {
      parallel {
        stage('build 2.0') {
          steps {
            echo 'success'
          }
        }

        stage('build 2.1') {
          steps {
            error 'some file exception'
          }
        }

        stage('build 2.2') {
          steps {
            echo 'success'
          }
        }

      }
    }

    stage('post build') {
      parallel {
        stage('success') {
          steps {
            echo 'success'
          }
        }

        stage('fail') {
          steps {
            echo 'fail'
          }
        }

      }
    }

  }
}