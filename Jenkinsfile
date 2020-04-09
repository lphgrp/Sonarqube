pipeline {
	agent any
	stages {
		stage ("--Code_Scan---") {
			steps {
				withSonarQubeEnv('Sonar_Qube') {
				  bat "D:\\LPH_Learning\\Installed_Soft\\sonar-scanner-4.2.0.1873-windows\\bin\\sonar-scanner -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=com.Sonar -Dsonar.projectName=SonarProject"
				}
			}
		}
		stage ("--Clean Project---") {
			steps {
				bat "mvn clean"
			}
		}
		stage ("--Create WarFile---") {
			steps {
				bat "mvn package"
			}
		}
		stage ("--Deploy WarFile---") {
			steps {
				bat "copy target\\MavenWeb.war D:\\LPH_Learning\\Installed_Soft\\Tomcat_Jenkins\\webapps\\"
			}
		}
	}
}