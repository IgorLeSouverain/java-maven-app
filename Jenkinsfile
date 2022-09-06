#!/usr/bin/env groovy

pipeline {
  agent none
  stages {
    stage('test') {
      steps {
        script {
          echo 'Testing the app...'
        }
      }
    }
    stage('build') {
      when {
        expression {
        }
      }
      steps {
        script {
          echo 'Building the app...'
        }
      }
    }
    stage('deploy') {
      when {
        expression {
        }
      }
      steps {
        script {
          echo 'Deploying the app...'
        }
      }
    }
  }
}
