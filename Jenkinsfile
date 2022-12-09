pipeline {
  agent any
  stages {
    stage('Build-1') {
      parallel {
        stage('Build') {
          steps {
            git(url: 'https://github.com/com2us-seongkyu/git-flow', changelog: true, credentialsId: 'github', poll: true, branch: 'master')
          }
        }

        stage('Build-2') {
          steps {
            git(url: 'https://github.com/com2us-seongkyu/git-flow', credentialsId: 'github', branch: 'qa', changelog: true, poll: true)
          }
        }

      }
    }

    stage('Check') {
      steps {
        sh 'echo check!'
      }
    }

  }
}