pipeline {
  agent any
  triggers{
      pollSCM('* * * * *')
  }
  stages{
   stage('git'){
     steps{
	     git url:'https://github.com/saikireeti123/spring-petclinic.git', branch:'dev'
	 }
   }
   stage('Build'){
      steps{
	    bat 'mvn clean validate package'
	  }
   }
  } 
  post{
    alWAYS{
      archieveartifacts artifacts:'**/target/*.jar'
    }
  }
}