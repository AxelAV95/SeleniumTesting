pipeline {
	agent any
    	stages {

	

        	stage('Pruebas de Selenium') {
            		steps {
                		echo "Ejecutando pruebas..."
				 bat '''
				selenium-side-runner -c "browserName=chrome" OrdenesCompraCicloSprint1.side 
                		'''
				
            		}
        	}

		
    }
    post {
        	always {
            		echo "Termino el test"
        	}				   			
	}
	 
}
