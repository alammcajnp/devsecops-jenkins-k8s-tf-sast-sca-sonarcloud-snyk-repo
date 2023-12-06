pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=alamdeen -Dsonar.organization=alam -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=fee9d8e6da78f8baf0b8ad30e9d2704b8e5ef83c'
			}
        }
      stage('RunSCAAnalysisUsingSnyk') {
                steps {		
                            withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
                                  sh 'mvn snyk:test -fn'
                            }
                      }
        } 
  }
}
