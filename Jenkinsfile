pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compiling sysfoo app...'
        sh 'mvn compile'
        sleep 3
      }
    }

    stage('test') {
      steps {
        echo 'testing sysfoo app...'
        sh 'mvn clean test'
        sleep 9
      }
    }

    stage('package') {
      steps {
        echo 'packaging sysfoo app...'
        sh 'mvn package -DskipTests'
        sleep 5
        archiveArtifacts 'target/*.war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}