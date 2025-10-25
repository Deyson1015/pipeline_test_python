pipeline {
    agent any

    environment {
        PYTHON = "python" // o python3 si está así en tu sistema
    }

    stages {
        stage('Clonar repositorio') {
            steps {
                git branch: 'main', url: 'https://github.com/Deyson1015/pipeline_test_python.git'
            }
        }

        stage('Instalar dependencias') {
            steps {
                echo 'Instalando dependencias...'
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Ejecutar pruebas unitarias') {
            steps {
                echo 'Ejecutando pruebas...'
                bat 'pytest -v'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completado correctamente.'
        }
        failure {
            echo '❌ El pipeline falló. Revisa los logs para más información.'
        }
    }
}
