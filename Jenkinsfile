pipeline {
	    agent any 
    	    stages {
	       
	        stage('compile') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
				       sh 'mvn compile'	 		  
	                  }
	            }
	        }
	        stage('Test') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
			   sh 'mvn test'  
	            }
	        }
		}
	        stage('package') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
			   sh 'mvn package'
	            }
	        }
		}
		     stage('sonar') { 
	            	steps {
	               withMaven(maven : 'Maven-3.5.4') {
	               sh 'mvn sonar:sonar -Dmaven.test.skip=true'
			
	            }
	        }
		}
		     stage('Deploy') { 
	                   steps {
	               withMaven(maven : 'Maven-3.5.4') {
	               sh 'mvn deploy -Dmaven.test.skip=true '
	                        }
	                   }
		     }
	    }
	}
