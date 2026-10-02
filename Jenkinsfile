pipeline {
 agent any
 stages {
  stage('Build') { steps { sh 'docker build -t notes-app:${BUILD_NUMBER}.' } }
  stage('Test') { steps { sh 'docker run -d -p 8080:80 --name test-${BUILD_NUMBER} notes-app:${BUILD_NUMBER} && sleep 5 && curl -f http://localhost:8080' } }
  stage('Push') { steps { echo 'Push to DockerHub' } }
 }
}
