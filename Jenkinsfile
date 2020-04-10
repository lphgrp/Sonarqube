pipeline {
	agent any
	stages {
		stage ("--Code_Scan---") {
			steps {
			    def sqScannerMsBuildHome = tool 'Sonar_Analysis'
				withSonarQubeEnv('Sonar_Server') {
				  bat "${sqScannerMsBuildHome}\\sonar-scanner.bat -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=com.Sonar -Dsonar.projectName=SonarProject"
				  }
			}
		}
		stage ("--Clean Project---") {
			steps {
				bat "mvn clean"
			}
		}
		stage ("--Create Jar---") {
			steps {
				bat "mvn package"
			}
		}
	}
}