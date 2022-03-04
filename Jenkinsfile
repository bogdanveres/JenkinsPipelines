pipeline {
    parameters {
      string defaultValue: 'defaultValue', name: 'testArg'
    }
    
    agent any

    stages {
        stage('Clean WS')
        {
            steps {
                cleanWs()
            }
        }
        
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'echo ${testArg}'
                sh 'echo "Added from snippet generator"'
            }
        }
    }
}
