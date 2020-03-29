pipeline {

  agent {
	  label 'windows'
    docker {
      image 'maven:3.6.3'
    }
  }

//agent { docker {image 'node:13.8'}}

stages {

stage('build'){
steps {
sh 'mvn --version'
echo "Build"
echo "$PATH"
echo "BUILD NUMNER -$env.BUILD_NUMBER"
echo "$env.BUILD_ID"
echo "$env.JOB_NAME"
echo "$env.BUILD_URL"
//sh 'node --version'
echo "build"
}
}
stage('Test') {
steps {
echo "Test"
}
}
stage('Integration Test') {
steps {
echo "Integration Test"
}
}
}
}
