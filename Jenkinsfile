pipeline {
	agent any
    	stages {

		 stage('Verificar Instalación de selenium-side-runner') {
            steps {
                script {
                    // Verificar si selenium-side-runner está instalado
                    def isInstalled = bat(script: 'selenium-side-runner --version', returnStatus: true) == 0
                    if (!isInstalled) {
                        echo "selenium-side-runner no está instalado. Instalando..."
                        // Instalar selenium-side-runner si no está instalado
                        bat 'npm install -g selenium-side-runner'
                    } else {
                        echo "selenium-side-runner ya está instalado."
                    }
                }
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
