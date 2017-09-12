pipeline {
  agent any
  stages {
    stage('Hello') {
      steps {
        sh 'echo "Hello Ed"'
      }
    }
    
   steps {
          sh '''docker-compose build
  docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)
 -docker-compose run ./scripts/setup.sh rails test
 +docker-compose run web ./scripts/setup.sh rails test
  '''
        }
      }
  }
}