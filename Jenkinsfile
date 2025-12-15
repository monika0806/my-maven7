pipeline {
  agent any

  tools {
    maven 'maven3'
    jdk 'jdk17'
  }

  stages {
    stage('Checkout') { steps { checkout scm } }

    stage('Build') {
      steps {
        sh 'mvn -B clean package'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
      }
    }
  }
}
