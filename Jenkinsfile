pipeline {
  agent any
  stages {
    stage('buildStage') {
      steps {
        git(url: 'https://github.com/indhugkrish/demorepo1', branch: 'master', credentialsId: 'a87ef90c-8f35-441b-ab57-ab82195ecd5e')
        sh '''docker build -t indhugkrish/jenkinsrepo1:latest
.'''
      }
    }

    stage('Dev&QA') {
      parallel {
        stage('devDeploy') {
          steps {
            sh 'docker push indhugkrish/jenkinsrepo1:latest'
          }
        }

        stage('deployQa') {
          steps {
            echo 'QA Deployed !!'
          }
        }

      }
    }

  }
}