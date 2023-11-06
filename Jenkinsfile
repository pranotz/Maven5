pipeline {
	agent any 
	triggers {
  pollSCM '* * * * *'
}

	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/pranotz/Documents/Devops_software/apache-maven-3.9.5/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/Maven5.war /home/pranotz/Documents/Devops_software/apache-tomcat-9.0.82/webapps'
			}}	
}}
