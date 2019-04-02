node ('master')
{
    stage ('continious download')
    {
        git 'https://github.com/selenium-saikrishna/maven.git'
    }
    stage ('continious build')
    {
       sh label: '', script: 'mvn package' 
    }
    stage ('continious deployment')
    {
      sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/pipesrict2/webapp/target/webapp.war ubuntu@172.31.46.243:/var/lib/tomcat8/webapps/qaenv.war'  
    }
    stage ('continious testing')
    {
        git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
    }
    stage ('continious delivery')
    {
      sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/pipesrict2/webapp/target/webapp.war ubuntu@172.31.36.147:/var/lib/tomcat8/webapps/prodenv.war'  
    }
}
