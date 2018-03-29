pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''git submodule init
git submodule update --recursive --remote

cd libsuinput
./autogen.sh
./configure
make
cd ..

gcc -std=c99 -Wall ./waveshare.c -pthread -lsuinput -ludev -Ilibsuinput/src -Llibsuinput/src/.libs -o waveshare-touch-driver'''
      }
    }
    stage('save') {
      steps {
        archiveArtifacts 'waveshare-touch-driver'
      }
    }
  }
}