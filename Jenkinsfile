pipeline {

  agent any

    stages {
      stage ('make compile') {
        steps {
          sh '''
            mvn compile
          '''
        }
      }
      stage (' make package') {
         steps {
           sh '''
             mvn package
           '''

         }
      }
      stage ('prepare artifact') {
        steps {

           sh '''

              cp target/*.jar users.jar && zip -r  ../users.zip * users.jar
           '''
        }
      }
      stage ('upload artifact') {
        steps {
          sh '''
           curl -f -v -u admin:vamsi --upload-file users.zip http://172.31.9.137:8081/repository/users1/users.zip

          '''
        }
      }
    }
 }
