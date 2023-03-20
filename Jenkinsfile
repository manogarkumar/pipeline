pipeline {
	agent { node { label 'node1' } }
		stages {
			stage ('CleanWorkSpace') {
				steps {
					cleanWs()
				}
			}
			stage ('git-clone') {
				steps {
					sh "git clone https://github.com/manogarkumar/pipeline.git"
				}
			}
			stage ('build-step') {
				steps {
					sh "mvn -f /home/ec2-user/hello-world/pom.xml clean install"
				}
			}
			stage ('deploy') {
				steps {
					sh "rm /home/ec2-user/tomcat8/webapps/webapp.war"
					sh "cp /home/ec2-user/hello-world/webapp/target/webapp.war /home/ec2-user/tomcat8/webapps"
				}
			}
		}
}
