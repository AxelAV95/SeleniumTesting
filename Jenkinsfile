pipeline {
	agent any
    	stages {

	stage('Verificar Instalación de Selenium-side-runner') {
            steps {
                echo "Verificando instalación de selenium-side-runner..."
                bat 'selenium-side-runner --version'
            }
        }

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
