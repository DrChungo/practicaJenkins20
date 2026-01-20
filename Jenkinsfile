pipeline {
    agent any

    environment {
        APP= "YAGO APP"
        ENTORNO="DEV"
        MENSAJE = 'practica de pipelines'
    }

    stages {
        stage('Info') {
            steps {
               
                echo "APP=${env.APP}"
                echo "ENTORNO=${env.ENTORNO}"
                echo "MENSAJE=${env.MENSAJE}"
            }
        }

        stage('Aprobacion') {
            steps {
                input message: "¿Continuar?", ok: 'Continuar'
            }
        }

        stage('despliegue') {
            steps {
                echo "Desplegando APP en ENTORNO…"
            }
        }
    }

    post {
        success {
            echo "OK: Yago exitoso."
        }
        failure {
            echo "ERROR: Yago fallido."
        }
        aborted {
            echo "CANCELADO: Yago cancelado manualmente"
        }
        always {
            echo "FIN: SE ACABO YAGOOOO"
        }
    }
}