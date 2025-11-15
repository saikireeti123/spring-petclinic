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
  always{
      archiveArtifacts artifacts:'**/target/*.jar'
	  junit '**/target/surefire-reports/*.xml'
  }
}

}