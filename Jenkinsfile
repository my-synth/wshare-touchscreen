pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''git submodule init

cd libsuinput
./autogen.sh
./configure
make
cd ..

gcc -std=c99 -Wall ./waveshare.c -pthread -lsuinput -ludev -Ilibsuinput/src -Llibsuinput/src -o waveshare-touch-driver'''
      }
    }
  }
}