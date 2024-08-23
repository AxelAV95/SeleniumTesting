pipeline {
    agent any
    stages {
        stage('Configurar entorno') {
            steps {
                echo "Configurando entorno..."
                sh '''
                # Añadir npm global bin al PATH
                export PATH=$PATH:$(npm bin -g)

                # Verificar instalación de selenium-side-runner y chromedriver
                which selenium-side-runner || { echo "selenium-side-runner no encontrado. Instalando..."; npm install -g selenium-side-runner; }
                which chromedriver || { echo "chromedriver no encontrado. Instalando..."; npm install -g chromedriver; }
                '''
            }
        }

        stage('Pruebas de Selenium') {
            steps {
                echo "Ejecutando pruebas..."
                sh '''
                export PATH=$PATH:$(npm bin -g)
                selenium-side-runner -c "browserName=chrome" OrdenesCompraCicloSprint1.side
                '''
            }
        }
    }
    post {
        always {
            echo "Terminó el test"
        }
    }
}
