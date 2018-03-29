pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''cd libsuinput
./autogen.sh
./configure
make
cd ..
'''
        sh 'gcc -std=c99 -Wall ./waveshare.c -pthread -lsuinput -ludev -Ilibsuinput/src -Llibsuinput/src -o waveshare-touch-driver'
      }
    }
  }
}