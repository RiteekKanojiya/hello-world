pipeline{
agent any
environment{
    PATH= "/usr/bin/mvn:$PATH"
}
  stages{
    stage("git"){
      steps{
            git 'https://github.com/RiteekKanojiya/hello-world.git'
    }
    
    }
    
    stage("build"){
      steps{
       sh "mvn -B -DskipTests clean package"    
    }
    }
     stage("deploy"){
      steps{
     sshagent(['riteek']) {
    sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.124.182.244:/opt/tomcat/webapps"
    
}
    }
    }
    
}
}
