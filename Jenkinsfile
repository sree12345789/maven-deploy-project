pipeline {

agent {
  label {
    label 'jenkins_agent'
    retries 3
  }
}

stages {
  stage('Checkout') {
    steps {
      step "checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-user', url: 'https://github.com/devopsdeepdive/maven-deploy-project.git']]])"
    }
  }
  stage ('Validate') {
   steps{
   sh 'mvn validate' 
    } 
   }
 }	
}
