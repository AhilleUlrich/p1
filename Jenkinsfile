pipeline {
  agent any
  stages {
    stage('clone githuh project') {
      steps {
        git(url: 'https://github.com/AhilleUlrich/pyton-unittest.git', branch: 'main')
      }
    }

    stage('execute test') {
      steps {
        sh 'pytest --junitxml test-results.xml "/tmp/calculator/temp.py"'
      }
    }

    stage('publish results') {
      steps {
        junit 'test*.xml'
      }
    }

  }
}