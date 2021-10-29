pipeline {
  agent any
  stages {
    stage('Build Env') {
      steps {
        sh '''python -m venv ${BUILD_TAG}/.venv
'''
        sh 'source ${BUILD_TAG}/.venv/bin/activate'
        sh 'pip install --upgrade pip'
        sh 'pip install -r requirements_dev.txt'
      }
    }

    stage('Test Environment') {
      steps {
        sh 'source ${BUILD_TAG}/.venv/bin/activate'
        sh 'tox '
      }
    }

  }
}