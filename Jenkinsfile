pipeline {
	agent any
	stages {
		stage ("--Code_Scan---") {
			steps {
				withSonarQubeEnv('Sonar_Server') {
				  bat "\'%Sonar_Analysis%\'/sonar-scanner.bat -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=com.Sonar -Dsonar.projectName=SonarProject"
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