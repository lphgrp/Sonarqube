pipeline {
	agent any
	stages {
		stage ("--Code_Scan---") {
			steps {
				def scannerhome = tool 'SonarScanner';
				withSonarQubeEnv('Sonar_Qube') {
				  bat "${scannerHome}/bin/sonar-scanner"
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