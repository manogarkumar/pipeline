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
					sh "git clone https://github.com/devopsjuly22/devops.git"
				}
			}
			stage ('build-step') {
				steps {
					sh "mvn -f /home/ec2-user/workspace/my_pipeline1/devops/pom.xml clean install"
				}
			}
			stage ('deploy') {
				steps {
					sh "rm /home/ec2-user/tomcat8/webapps/webapp.war"
					sh "cp /home/ec2-user/workspace/my-pipeline1/devops/webapp/target/webapp.war /home/ec2-user/tomcat8/webapps"
				}
			}
		}
}
