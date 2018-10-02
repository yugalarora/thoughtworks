pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/yugalarora/thoughtworks.git', branch: 'master', changelog: true)
      }
    }
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "in Build Stage"'
            echo 'Build Succesful'
          }
        }
        stage('ParallelToBuild') {
          steps {
            timestamps() {
              echo 'ParallelToBuild :: Step'
            }

          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'in Deploy Stage'
      }
    }
  }
}
