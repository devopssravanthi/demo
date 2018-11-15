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
	              
			   sh 'mvn test'  
	            }
	        }
	        stage('package') { 
	            steps {
	            
			   sh 'mvn package'
	            }
	        }
		     stage('sonar') { 
	            	steps {
	               sh 'mvn sonar:sonar -Dmaven.test.skip=true'
			
	            }
	        }
		     stage('Deploy') { 
	                   steps {
			
	               sh 'mvn deploy -Dmaven.test.skip=true '
	                        }
	                   }
	    }
	}
