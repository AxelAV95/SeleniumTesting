pipeline {
    agent any
    stages {
        stage('Verificar Instalación de selenium-side-runner') {
            steps {
                script {
                    // Verificar si selenium-side-runner está instalado
                    def isInstalled = sh(script: "which selenium-side-runner", returnStatus: true) == 0
                    if (!isInstalled) {
                        echo "selenium-side-runner no está instalado. Instalando..."
                        sh 'npm install -g selenium-side-runner'
                        sh 'npm install -g chromedriver'
                    } else {
                        echo "selenium-side-runner ya está instalado."
                    }
                }
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
