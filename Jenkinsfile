pipeline {

	agent any
	tools{
		jdk 'Java17'
		maven 'Maven3'
	}
	

	triggers{
		pollSCM('H/2 * * * *')
	}

	stages{
		stage("Clean Workspace"){
			steps{
			cleanWs()
			
			}
		}
		
		stage("Checkout from SCM"){
			steps{
				git branch: 'main', credentialsId: 'github', url: 'https://github.com/ashrithasgit/register-app-yash.git'
			}					
		}
		stage("Build Application"){
			steps{
				sh "mvn clean package"
			}		
		}
		stage("Test"){
			steps{
				sh "mvn test"
			}
		}
	}	
}
