pipeline {
	agent any

	tools {
   	 
    	maven "maven 3.6.0"
	}

	stages {
    	stage('Build') {
        	steps {
           	 
            	git 'https://github.com/gauravk29/admin.git'

           	 
            	sh "mvn -Dmaven.test.failure.ignore=true clean package"

        	}

        	post {
           	 
            	success {
                	junit '**/target/surefire-reports/TEST-*.xml'
                	archiveArtifacts 'target/*.jar'
            	}
        	}
    	}
	}
}
