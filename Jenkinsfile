pipeline {
  agent any
  stages {
    stage('stage 1') {
      steps {
        sh 'Grep user /etc/passwd'
      }
    }

    stage('stage 2') {
      parallel {
        stage('stage 2') {
          steps {
            sh '''if test `grep -c user /etc/passwd` -ne 0
then
find / -user user > /tmp/user
fi'''
          }
        }

        stage('stage 3') {
          steps {
            sh '''For i in `cat /tmp/user`
Do
Ls -il $i
done'''
          }
        }

        stage('') {
          steps {
            sh 'date'
          }
        }

      }
    }

  }
}