pipeline{
agent any 
options {
  buildDiscarder logRotator(artifactDaysToKeepStr: '2', artifactNumToKeepStr: '2', daysToKeepStr: '', numToKeepStr: '2')
}
 tools { nodejs "Suji" }
 stages {
	stage('Checkout code') {
	steps {
 git credentialsId: 'e0e91656-881b-4e6c-a045-0d113dff0754',
            url: 'https://github.com/g7007226-lab/nodejs-app-mss.git'
}
}
stage ('Building') {
steps  {
sh "npm install" 
 } 
 }
 stage('Sonar report') {
     steps {
         sh "npm run sonar"
     }
 }
 stage('Deploying artifacts') {
     steps { 
         sh "npm run start &"
 }
 }
}
}
