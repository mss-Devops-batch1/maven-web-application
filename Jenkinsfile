node{

def mavenHome = tool name: "maven3.8.5"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])


stage('checkoutcode')
{
git branch: 'development', credentialsId: '22384751-4d83-4918-8997-0b8767fa4ef2', url: 'https://github.com/mss-Devops-batch1/maven-web-application.git'
}

stage('build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactsIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppIntoTomcatServer')
{
sshagent(['e4d4f30f-3ae9-4b67-895e-a66a490f3742']) {
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.45.150:/opt/apache-tomcat-9.0.63/webapps"
}

}
*/

}
