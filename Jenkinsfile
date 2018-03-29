pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'gcc -std=c99 -Wall ./waveshare.c -pthread -lsuinput -ludev -o waveshare-touch-driver'
      }
    }
  }
}