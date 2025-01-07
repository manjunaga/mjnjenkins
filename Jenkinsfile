pipeline {
    agent any
    tools { go 'go1.23.4' } // Comes from the jenkins global config
    
    environment {
        ENV = "${env.BRANCH_NAME == 'master' ? 'PROD' : 'DEV'}"
    }
    stages {
        stage('Build') {
            steps {
                sh 'bash scripts/build.sh' // Run the build.sh asset
            }
        }
        stage('Test') {
            steps {
                sh 'bash scripts/test.sh' // Run the test.sh asset
            }
        }
    }
}