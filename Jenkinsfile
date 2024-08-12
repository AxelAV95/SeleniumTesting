pipeline {
	agent any
    	stages {

		stage('Instalar selenium-side-runner') {
            steps {
                echo "Instalando selenium-side-runner..."
                bat 'npm install -g selenium-side-runner'
            }
        }
	stage('Verificar Instalación de Selenium-side-runner') {
            steps {
                echo "Verificando instalacion de selenium-side-runner..."
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
