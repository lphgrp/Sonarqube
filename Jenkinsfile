pipeline {
	agent any
	stages {
		stage ("--Code_Scan---") {
			steps {
				withSonarQubeEnv('Sonar_Analysis') {
				  bat "D:\\InstallSoft\\sonar-scanner-4.2.0.1873-windows\\bin\\sonar-scanner -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=com.Sonar -Dsonar.projectName=SonarProject"
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