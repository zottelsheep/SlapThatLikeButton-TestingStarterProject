pipeline {
  agent any
  stages {
    stage('Build Env') {
      steps {
        sh '''python -m venv ${BUILD_TAG}/.venv
        . ${BUILD_TAG}/.venv/bin/activate
        pip install --upgrade pip
        pip install -r requirements_dev.txt
        '''
      }
    }

    stage('Test Environment') {
      steps {
        sh '''. ${BUILD_TAG}/.venv/bin/activate
        tox
        '''
      }
    }

  }
}
