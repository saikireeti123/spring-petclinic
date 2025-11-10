pipeline{
  agent any
  trigeer
   {
        pollSCM('H/5 * * * *')
    }
	stages{
	  stage('git'){
	    steps 
            {
                git branch: 'dev', url:'https://github.com/saikireeti123/spring-petclinic.git'
            }
	}
	  stage('Build'){
	      steps{
	       echo "Build started"
	        bat mvn clean validate package
	           }
	
	        }
        }
   }
   