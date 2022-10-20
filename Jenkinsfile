pipeline {
  agent any
  stages {
    stage('Hello') {
      parallel {
        stage('Hello') {
          steps {
            echo 'Hello World'
            sh 'echo ${testArg}'
            sh 'echo "Added from snippet generator"'
          }
        }

        stage('Hello 2') {
          steps {
            echo 'Test message'
          }
        }

      }
    }

    stage('Execute shell') {
      agent {
        label 'MacOS'
      }
      steps {
        sh 'ls'
        sh 'chmod +x HelloWorld.sh'
        sh './HelloWorld.sh'
      }
    }

    stage('Clean WS') {
      steps {
        cleanWs()
      }
    }

  }
  parameters {
    string(defaultValue: 'defaultNewValue', name: 'testArg')
  }
}
