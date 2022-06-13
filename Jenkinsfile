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
                 ./bin/lokalise2 \
                   --token a701f9bb80485535e3c314f4e39ad09511842ef5 \
                   --project-id 1878556462a719c3454886.17115275 \
                   file download \
                   --format xliff \
                   --all-platforms \
                   --bundle-structure "messages.%LANG_ISO%.xlf" \
                   --original-filenames=false \
                   --unzip-to src/i18n
                 docker-compose build
                 docker-compose stop
                 docker-compose up -d
                 '''
             }
         }
    }
}
