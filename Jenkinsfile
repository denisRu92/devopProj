pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://github.com/contentful/the-example-app.nodejs.git', branch: 'master')
        sh 'npm install'
      }
    }
    stage('Test') {
            steps {
                sh './test.sh'
            }
        }
    
  
    stage('Deliver') {
            steps {
                sh './deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './kill.sh'
            }
        }
    }
}
