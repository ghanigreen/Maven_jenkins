node ("node1"){
    
    stage("scm")
    {
    git 'https://github.com/ghanigreen/maven_demo.git'
    }
    stage ("build")
    {
    sh 'mvn clean install'
    }
    stage ("Sonarqube")
    sh 'mvn sonar:sonar'
    stage ("junit testing")
    junit '**/surefire-reports/*.xml'
    stage ("Artifactory")
    archiveArtifacts '**/*.war'
    stage("deploy")
    sh label: '', script: 'sudo cp -R "/var/lib/jenkins/workspace/pipeline1/gameoflife-web/target/gameoflife.war"  "/opt/tomcat/apache-tomcat-9.0.17/webapps/"'
    
    
    
    
}
