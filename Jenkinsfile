pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/YuvalSal99/NodeJS-EmptySiteTemplate.git', branch: 'master')
      }
    }

    stage('build') {
      steps {
        sh 'npm install'
        sleep 5
        sh 'npm run start &'
      }
    }

    stage('test') {
      steps {
        sh 'curl localhost:8080'
      }
    }

    stage('package') {
      steps {
        sh 'tar czvf nodeejs.tar.gz *'
      }
    }

    stage('archive') {
      steps {
        archiveArtifacts '*.tar.gz'
      }
    }

  }
}