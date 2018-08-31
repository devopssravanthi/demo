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
	              
			   bat 'mvn test'
			  
	            }
	        }
	        stage('package') { 
	            steps {
	            
			   bat 'mvn package'
	            }
	        }
		     stage('sonar') { 
	            	steps {
	               bat 'mvn sonar:sonar -Dmaven.test.skip=true'
			
	            }
	        }
		    
		    
		  //   stage('Deploy') { 
	           // steps {
			
	               //bat 'mvn deploy -Dmaven.test.skip=true '
	           // }
	        //}
	    }
	}
