import org.jenkinsci.plugins.workflow.steps.FlowInterruptedException

pipeline {

	agent none



	environment {
	    MyKeyID="myCustomValue1"
	}
	
	stages {
	
stage("stage master") {
		steps {
    			script {
					
					stage("inner stage 1") {
						script {
						
							/*node {
								println "inner stage"
							}
							*/
							try{
							    timeout(time: 60, unit:"SECONDS") {
							        input(messsage:"Esta seguro de hacer el deply???")
							    }
							}
							catch(Exception error)
							{
							    def user = error.getCauses()[0].getUser().toString();
							    if(user=="SYSTEM") {
							        println "Ejecucion abortada por usuario de sistema ${user}"
							    }
							    else
							    {
							        println "Ejecucion abortada por usuario de sistema ${user}"
							    }
							    
							}

							
						}
					}

					stage("inner stage 2") {
						script {
						
							node {
								println "inner stage"
							}

							
						}
					}

		
							

						}
					}
				}

	stage('Descargar codigo fuente') {
	    environment {
    	    MyKeyID="myCustomValue2x"
    	}
    	steps {
    		script {
          		node {
        				println "\n Mi primer stage.\n MyKeyID value es: ${MyKeyID}\n"
          		}
        	}
    	}
	} 
	
	stage('Test') {
    	steps {
    		script {
          		node {
        			println "Mi segundo stage esta en ejecucion. KeyID: $MyKeyID"
          		}
        	}
    	}
	}
	
	stage('Fin') {
    	steps {
    		script {
          		node {
        			println "Mi segundo stage esta en ejecucion. KeyID: $MyKeyID"
          		}
        	}
    	}
	}
	    
}

}
