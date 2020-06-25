pipeline {
   agent any

  stages {
      stage('Get the code') {
         steps {
            git 'https://github.com/iamdevopstrainer/DevOpsClassCodes.git'
         }
      }
      
            stage('Compile the code') {
         steps {
          sh  '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven361/bin/mvn compile'
         }
      }
      
      stage('Test') {
         steps {
           sh  '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven361/bin/mvn test'
         }
      }
      
  stage('Package') {
         steps {
            sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven361/bin/mvn package'
         }
      }
      
stage('Deploy') {
         steps {
             echo "Deployment"
            sh 'sudo cp /var/lib/jenkins/workspace/pipeline project/target/addressbook.war /usr/share/tomcat/webapps'
            sh 'sudo systemctl restart tomcat'
         }
      }
      
}
}
