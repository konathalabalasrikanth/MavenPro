node('master') 
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/konathalabalasrikanth/maven.git'             
    }
    stage('ContinuousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
	sh 'scp /root/.jenkins/workspace/Jenkins_pipeline/webapp/target/webapp.war root@10.0.2.116:/var/lib/tomcat8/webapps/testapp.war'
    }

    stage('ContinuousTesting')
    {
        git 'https://github.com/konathalabalasrikanth/FunctionalTesting.git'
        sh 'java -jar /root/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
    stage('ContinuousDelivery')
    {
    
    //sh 'scp /root/.jenkins/workspace/Jenkins_pipeline/webapp/target/webapp.war ubuntu@172.31.28.60:/var/lib/tomcat9/webapps/prodapp.war'
    }
}
