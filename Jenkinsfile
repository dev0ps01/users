pipeline {
    agent any
    stages {
         stage('compile code') {
             steps {
                  sh '''
                    mvn compile
                  '''
             }
         }
         stage('make package') {
             steps {
                 sh '''

                     mvn package
                 '''
             }
         }
         stage ('Prepare Artifacts') {
           steps {
               sh '''
                  zip -r users.zip *
               '''
           }
         }
       stage('Upload Artifacts') {
          steps {
              script {
                   nexus
              }
          }
       }
    }
}
