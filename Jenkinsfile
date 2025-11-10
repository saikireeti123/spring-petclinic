pipeline{
  agent any
  triggers
    {
        pollSCM('* * * * *')
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
	        bat 'mvn clean validate package'
	           }
	
	        }
        }
		post{
		always{
		archiveArtifacts artifacts: '**/target/*.jar'
		}
		
		}
   }
   