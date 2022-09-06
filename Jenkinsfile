#!/usr/bin/env groovy

library identifier: 'jenkins-shared-library@master', retriever: modernSCM(
    [$class: 'GitSCMSource',
    remote: 'https://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@github.com/IgorTheOverlord/jenkins-shared-library.git',
    credentialsId: 'github-credentials']
)

def gv

pipeline {
  agent any
  tools {
    maven 'Maven'
  }
  stages {
    stage("init") {
      steps {
        script {
          gv = load "script.groovy"
        }
      }
    }
    stage("build jar") {
      steps {
        script {
          buildJar()
        }
      }
    }
    stage("build image") {
      steps {
        script {
          buildImage 'igortheoverlord1/demo-app:jma-3.0'
          dockerLogin()
          dockerPush 'igortheoverlord1/demo-app:jma-3.0'
        }
      }
    }
    stage("deploy") {
      steps {
        script {
          gv.deployApp()
        }
      }
    }
  }
}
