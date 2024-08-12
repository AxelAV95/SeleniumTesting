pipeline {
	agent any
    	stages {

		stage('Verificar Instalacion de selenium-side-runner') {
            steps {
                script {
                    // Definir el directorio npm global (ajusta la ruta si es diferente)
                    def npmGlobalPath = 'C:\\Users\\AxelAV.LAPTOP-FF6SODJH\\AppData\\Roaming\\npm'
                    
                    // Agregar el directorio npm al PATH temporalmente
                    def isInstalled = bat(script: "set PATH=%PATH%;${npmGlobalPath} && selenium-side-runner --version", returnStatus: true) == 0
                    if (!isInstalled) {
                        echo "selenium-side-runner no está instalado. Instalando..."
                        bat "npm install -g selenium-side-runner"
                    } else {
                        echo "selenium-side-runner ya está instalado."
                    }
                }
            }
        }
	

        	stage('Pruebas de Selenium') {
            steps {
                echo "Ejecutando pruebas..."
                bat '''
                set PATH=%PATH%;C:\\Users\\AxelAV.LAPTOP-FF6SODJH\\AppData\\Roaming\\npm
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
