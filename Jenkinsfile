pipeline {
    agent any

    environment {
        APPID = 'fb60ef31-1a99-462d-a9f1-c3b243baf2f8'
        TENANT = '42d1caad-48a6-43bd-a6dd-eb0a9d0abd43'
        PASSWORD = credentials('password-account-patricia')
        APP_NAME = 'Python-App-patricia'
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

        stage("Deploy App"){
            steps{
                echo "=== LOGIN TO AZURE ==="
                sh "az login --service-principal --username ${APPID} --password ${PASSWORD} --tenant ${TENANT}"
                echo "=== DEPLOYING APP ==="
                sh "az webapp up --runtime PYTHON:3.9 --sku B1 --resource-group rg-proteus-infra --name ${APP_NAME}"
                echo "=== LOGOUT TO AZURE ==="
                sh "az logout"
            }
        }
    }
}
