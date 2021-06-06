pipeline {
  agent any
  stages {
    stage('Build stage') {
      parallel {
        stage('Build stage') {
          steps {
            echo 'Build stage'
            dir(path: 'C:\\Users\\Aakarsh Yoga 7i\\Personal Documents\\01_Git_repositories\\AR_devops') {
              bat(script: 'run_script.bat', returnStatus: true, returnStdout: true, encoding: 'utf-8')
            }

            echo 'Build and execution successful!'
          }
        }

        stage('Present working directory?') {
          steps {
            pwd()
          }
        }

      }
    }

  }
}