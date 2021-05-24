pipeline {
    agent any
    stages {
         stage ('Prepare Artifacts') {
           steps {
               sh '''
                  zip -r users.zip *
               '''
           }
         }
       stage('Upload Artifacts') {
          steps {
              sh '''

                 curl -f -v -u admin:vamsi --upload-file users.zip http://172.31.9.137:8081/repository/users/users.zip
              '''
          }
       }
    }
}
