// start of pipeline
pipeline {
 // where pipeline job will run
 agent {
 // force pipeline job to running on windows_agent
 label "Windows_Agent"
 }
 // start of stages : build, test, deploy ...
 stages {
 // start of build stage
 stage('build') {
 // define step to run
 steps {
 // invoke command to build with maven
 bat 'mvn clean install'
 }
 }
 // start of deploy state
 stage('deploy') {
 // define step to run
 steps {
 //invoke command to stop tomcat service
 bat 'sc stop Tomcat8'
 bat 'ping 127.0.0.1 -n 6'
 // copy war file from build target to webapp Tomcat folder
 bat 'xcopy /y
C:\\Jenkins_Slave\\workspace\\GOL_Pipeline\\gameoflifeweb\\target\\gameoflife.war "C:\\Program Files\\Apache Software
Foundation\\Tomcat 8.5\\webapps"'
 //invoke command to start tomcat service
 bat 'sc start Tomcat8'
 }
 }
 }
}
