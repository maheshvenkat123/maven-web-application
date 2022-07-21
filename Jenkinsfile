node
{
    def mavenHome = tool name: "maven3.8.1"
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
    stage('CheckoutCode')
    {
        git branch: 'development', credentialsId: 'fc7072f7-908e-4c90-97e0-5139f44b865c', url: 'https://github.com/maheshvenkat123/maven-web-application.git'
    }
    stage('Build')
    {
        sh "${mavenHome}/bin/mvn clean package"
    }
    /*
    stage('ExecuteSonarQubeReport')
    {
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    stage('UploadArtifactsintoNexus')
    {
        sh "${mavenHome}/bin/mvn deploy"
    }
    stage('DeployAppintoTomcatServer')
    {
    sshagent(['4e6ff056-ff11-4aec-bc8c-99407f43858e']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.0.131.150:/opt/apache-tomcat-9.0.64/webapps/"
    }
    }
    */
}
