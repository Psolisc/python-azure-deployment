pipeline {
    agent any

    environment {
        CARRO = 'Nissan'
    }

    stages{
        stage("Verificar Python"){
            steps {
                sh "python3 --version"
            }
        }

        stage("Instalar Dependencias"){
            steps{
                sh "pip3 install -r requirements.txt"
            }
        }
    }
}