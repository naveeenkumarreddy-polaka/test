#!groovy

pipeline{
	agent any
	stages{
		stage('git checkout'){
			steps{
				git changelog: false, credentialsId: 'testgit', poll: false, url: 'https://github.com/naveeenkumarreddy-polaka/test.git'
			}
		}
		stage('Sonar Scan'){
			steps{
				bat "mvn sonar:sonar install"
			}
		}
		
		

		stage('Deploy'){
			steps{
				bat "mvn clean deploy"
			}
		}
		stage('Deploy'){
			steps{
				bat 'copy "C:\\Program Files (x86)\\Jenkins\\workspace\\test\\target\\*.war" C:\\Users\\qw693\\Documents\\Devops_tools\\apache-tomcat-8.5.40\\webapps'
			}
		}
	}
}
