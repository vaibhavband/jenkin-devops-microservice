pipeline {
//agent any
agent { docker {image 'maven:3.6.3'}}
//agent { docker {image 'node 13.8'}}
stages {

stage('build'){
steps {
sh 'mvn --version'
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
