pipeline {
    agent any

    environment {
        APPID = '35e538ca-825a-4f7d-bb6c-0daaaa0c681a'
        TENANT = '25600acd-d1ea-40ed-b091-46a5c1489762'
        PASSWORD = credentials('password-account')
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

        stage("Azure Login"){
            steps{
                sh "az login --service-principal --username ${APPID} --password ${PASSWORD} --tenant ${TENANT}"
            }
        }
    }
}