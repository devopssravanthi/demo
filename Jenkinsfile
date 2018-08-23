pipeline {
	    agent any 
		
	    stages {
	       
	           
	        stage('compile') { 
	            steps {
	                   withMaven(maven : 'Maven-3.5.4') {
				 // sh 'mvn compile -Dparams.version="${params.version}"'
				  //sh 'mvn compile'
				       bat 'mvn compile'
				 // bat 'mvn compile -Dparams.version=%params.version%'
				  
	                  }
	            }
	        }
	        stage('Test') { 
	            steps {
	               //sh 'mvn test'
			    bat 'mvn test'
			    //bat 'mvn test -Dparams.version=%params.version%' 
	            }
	        }
	        stage('package') { 
	            steps {
	              // bat 'mvn package -Dmaven.test.skip=true -Dparams.version=%params.version%'
			   // sh 'mvn package'
			    bat 'mvn package'
	            }
	        }
		     stage('sonar') { 
	            	steps {
	               	 bat 'mvn sonar:sonar -Dmaven.test.skip=true -Dsonar.host.url=%sonar.host.url%'
			//   sh 'mvn sonar:sonar'
	            }
	        }
		    
		    
		  //   stage('Deploy') { 
	           // steps {
			//    sh 'mvn deploy'
	               //bat 'mvn deploy -Dmaven.test.skip=true -Dparams.version=%params.version%' 
	           // }
	        //}
	    }
	}
