pipeline {
	    agent any 
    	    stages {
	       
	        stage('compile') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
				       bat 'mvn compile'	 		  
	                  }
	            }
	        }
	        stage('Test') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
			   bat 'mvn test'  
	            }
	        }
		}
	        stage('package') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
			   bat 'mvn package'
	            }
	        }
		}
		     stage('sonar') { 
	            	steps {
	               withMaven(maven : 'Maven-3.5.4') {
	               bat 'mvn sonar:sonar -Dmaven.test.skip=true'
			
	            }
	        }
		}
		     stage('Deploy') { 
	                   steps {
	               withMaven(maven : 'Maven-3.5.4') {
	               bat 'mvn deploy -Dmaven.test.skip=true '
	                        }
	                   }
		     }
	    
	    }
	}
