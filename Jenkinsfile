pipeline {
    agent any
    
    stages {
    	
        stage('Build') {
           steps {
                bat 'mvn clean install'
                }
        }
        stage('Deploy') {
        	environment {
        		muleuser = credentials('user')
        		mulepwd = credentials('password')
        	}
        	
            steps {
            	echo "${muleuser}"
                bat "mvn deploy -Dusername=${muleuser} -Dpassword=${mulepwd} -DmuleDeploy"
                }
        }
    }
}