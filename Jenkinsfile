node{
  stage ('scm checkout'){
      git 'https://github.com/javahometech/my-app'	  
   }
  stage('compile'){
	  def mvnHome = tool name: 'mvn', type: 'maven'
	  sh "${mvnHome}/bin/mvn package"
	   }
	   
  stage ('Deploy'){
  sshagent(['jenkins']) {
  sh 'mv target/myweb-0.0.7-SNAPSHOT.war /root/tomcat8/webapps/'
}
  }	
