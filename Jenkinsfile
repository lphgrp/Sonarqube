pipeline {
	agent any
	environment {
        def sqScannerMsBuildHome = tool 'Sonar_Analysis'
    }
	stages {
		stage ("--Code_Scan---") {
			steps {
			      withSonarQubeEnv('Sonar_Server') {
				  bat "${sqScannerMsBuildHome}\\sonar-scanner -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=com.Sonar -Dsonar.projectName=SonarProject"
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