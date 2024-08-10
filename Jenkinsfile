pipeline {
  agent any
  tools { 
        maven 'maven_3_2_5'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=buggyapp2024 -Dsonar.organization=buggyapp2024 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=deb7eebafc9c18397e13cabb009f71245dc5ed36'
			}
        }
  }
}
