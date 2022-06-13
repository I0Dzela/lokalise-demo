pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('docker rebuild/restart') {
             steps {
                 sh '''
                 docker-compose build
                 docker-compose stop
                 docker-compose up -d
                 '''
             }
         }
    }
}
