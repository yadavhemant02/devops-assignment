pipeline {
agent any

tools{
maven "maven3.6"
}


stages {

stage("Checkout code"){
steps
{
checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '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', url: 'https://github.com/yadavhemant02/devops-assignment.git']]])
echo 'Check Out'
}
}
stage('Clean') {
steps {
bat 'mvn -f devops-assignment/pom.xml clean'
echo 'Cleaning..'
}
}
stage('Compile') {
steps {
bat 'mvn -f devops-assignment/pom.xml compile'
echo 'Compiling..'
}
}
stage('Test') {
steps {
bat 'mvn -f devops-assignment/pom.xml test'
echo 'Testing..'
}
}
stage('Packaging') {
steps {
bat 'mvn -f devops-assignment/pom.xml package'
echo 'Packageing..'
}
}
stage('Install') {
steps {
bat 'mvn -f devops-assignment/pom.xml install'
echo 'Installing..'
}
}


}
}
