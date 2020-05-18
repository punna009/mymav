node('master')
{
   stage('ContinuousTesting_loans')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
       
   }
   stage('ContinuousDelivery_loans')
   {
       input message: 'Waiting for Approval from the DM!', submitter: 'srinivas'
       sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.26.41:/var/lib/tomcat8/webapps/prodapp.war'
   }
   
   
}
