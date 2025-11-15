pipeline{
  agent any
  triggers{
      pollSCM('H/2 * * * *')
  }
  stages{
   stage('git'){
     steps{
	     git url:'https://github.com/saikireeti123/spring-petclinic.git'
		 git branch:'dev'
	 }
   }
   stage('Build'){
      steps{
	    bat 'mvn clean validate package'
	  }
   }
  } 
}