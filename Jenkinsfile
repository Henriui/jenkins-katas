pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "Hello world"'
          }
        }

        stage('build app') {
          agent {
            docker {
              image 'gradle:6-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}