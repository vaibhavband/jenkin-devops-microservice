pipeline {

agent any
  //agent { docker {image 'node:13.8'}}
  environment{
	dockerHome = tool 'myDocker'
	mavenHome = tool 'myMaven'
	PATH  "$dockerHome/bin:$mavenHome/bin:$PATH"
  }

stages {

stage('build'){
steps {
//sh 'mvn --version'
echo "Build"
echo "$PATH"
echo "BUILD NUMNER -$env.BUILD_NUMBER"
echo "BUILD Id -$env.BUILD_ID"
echo "BUILD job name -$env.JOB_NAME"
echo "BUILD URL -$env.BUILD_URL"
echo "BUILD TAG -$env.BUILD_TAG"
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
