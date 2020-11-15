node('master') 
{
    stage('Continuos Download') 
    {
    git 'https://github.com/Nayab244/maven.git'
    }
    stage('Continuos Build') 
    {
    sh 'mvn package'
    }
    stage('Continuos Deployment') 
    {
    sh 'scp /var/lib/jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war jenkins@172.31.38.176:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('Continuos Testing') 
    {
    git 'https://github.com/Nayab244/FunctionalTesting.git'
    sh 'java -jar /var/lib/jenkins/workspace/ScriptedPipeline/testing.jar'
    }
    stage('Continuos Delivery') 
    {
    sh 'scp /var/lib/jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war jenkins@172.31.35.101:/var/lib/tomcat8/webapps/prodapp.war'
    }
}

