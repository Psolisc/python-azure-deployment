pipeline {
    agent any

    environment {
        CARRO = 'Nissan'
    }

    stages{
        stage("Verificar Python"){
            sh "python3 --version"
        }

        stage("Instalar Dependencias"){
            sh "pip3 install -r requirements.txt"
        }
    }
}