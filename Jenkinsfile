node('master') 
{
   stage('ContinuosDownload') 
   {
    git 'https://github.com/Nayab244/maven.git'
   }
   stage('ContinuosBuild') 
   {
    sh 'mvn package'
   }
   stage('ContinuosDeployment') 
   {
    sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.33.5:/var/lib/tomcat8/webapps/testapp.war'
   }
   stage('ContinuosTesting') 
   {
    git 'https://github.com/Nayab244/FunctionalTesting.git'
    sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
   }
   stage('ContinuosDelivery') 
   {
    sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.37.148:/var/lib/tomcat8/webapps/prodapp.war'
   }
}
   
