pipeline {

agent any
  //agent { docker {image 'node:13.8'}}
  environment {
	dockerHome = tool 'myDocker'
	mavenHome = tool 'myMaven'
	PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  }

stages {

stage('checkout'){
steps {
bat 'mvn --version'
bat 'docker version'

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
stage('build') {
steps {
 bat "mvn clean compile" 
}
}
stage('Test') {
steps {
  echo "Integration Test"
//bat "mvn test"
}
}
stage('Integration Test') {
steps {
echo "Integration Test"
//bat "mvn failsafe: integration-test failsafe:verify "
}
}
stage('Package') {
steps {
  bat "mvn package -DskipTests"
//bat "mvn test"
}
}
stage('build docker image') {
steps {
echo "Integration Test"
//docker build -t vaibhavband/currency-exchange-devops:${env.BUILD_TAG}
script {

dockerimage=docker.build("vaibhavband/currency-exchange-devops:${env.BUILD_TAG} ")

}
}
}
stage('push docker image') {
steps {

script {
docker.withRegistry ('','dockerHub'){
dockerimage.push();
dockerimage.push(latest);
}
}
}
}
}
post{
always {

  echo "always"
}
success {

  echo "success"
}
failure {

  echo "failure"
}



}
}
