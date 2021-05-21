node
{
 
 def mavenHome = tool name : "maven3.8.1"
 
 //properties([pipelineTriggers([pollSCM('* * * * *')])])
 properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])]) 

 stage('CheckoutCode')
 {
 git branch: 'development', credentialsId: '0d1b9b9a-d295-4f8e-9cfa-34922a21bb93', url: 'https://github.com/mnp-projects/maven-web-application.git'
 }
 /*
 stage ('Build')
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 
 stage ('ExecuteSonarQubeReport')
 {
 sh "${mavenHome}/bin/mvn sonar:sonar"
 }
 
 stage ('UploadArtifactsintoNexus')
 {
 sh "${mavenHome}/bin/mvn deploy"
 }
 
 stage ('DeployAppintoTomcatServer')
 {
 sshagent(['084134bd-0ebe-4ce2-821b-de7b99548ee2']) {
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.2.33.132:/opt/apache-tomcat-9.0.45/webapps/"
 }
 }
 */
 stage ('SendEmailNotification')
 {
 emailext body: '''Build Over..

 Regards,
 Naga Pullaiah,
 7386063068.''', subject: 'Build Over..', to: 'nagapullaiahm94@gmail.com'
 }
  

}
