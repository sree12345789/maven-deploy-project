pipeline {
  agent any

stages {
  stage('Checkout') {
    steps {
      checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-user', url: 'https://github.com/devopsdeepdive/maven-deploy-project.git']]])
    }
  }
  
  stage('Validate') {
    steps {
      sh 'mvn validate'
    }
  }
  stage('Compile') {
    steps {
      sh 'mvn compile'
    }
  }
  stage('Package') {
    steps {
      sh '-Dmaven.test.skip=true package'
    }
  }

}
}

