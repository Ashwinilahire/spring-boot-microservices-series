pipeline {
    agent any
      
    stages {
        stage('Clone'){
            steps{
                git 'https://github.com/Ashwinilahire/spring-boot-microservices-series.git'
            }
        }
        stage('Build'){
            steps{
                sh './mvnw clean package -DskipTests=true'
            }
        }
        stage('config-server docker image'){
            steps{
                dir('config-server'){
                    sh "docker build -t config-server:${env.BUILD_ID} ."
                }
            }
        }
        stage('service-registry docker image'){
            steps{
                dir('service-registry'){
                    sh "docker build -t service-registry:${env.BUILD_ID} ."
                }
            }
        }
        stage('hystrix-dashboard docker image'){
            steps{
                dir('hystrix-dashboard'){
                    sh "docker build -t hystrix-dashboard:${env.BUILD_ID} ."
                }
            }
        }
        stage('catalog-service docker image'){
            steps{
                dir('catalog-service'){
                    sh "docker build -t catalog-service:${env.BUILD_ID} ."
                }
            }
        }
        stage('inventory-service docker image'){
            steps{
                dir('inventory-service'){
                   sh "docker build -t inventory-service:${env.BUILD_ID} ."
                }
            }
        }
        stage('order-service docker image'){
            steps{
                dir('order-service'){
                    sh "docker build -t order-service:${env.BUILD_ID} ."
                }
            }
        }   
        stage('shoppingcart-ui docker image'){
            steps{
                dir('shoppingcart-ui'){
                    sh "docker build -t shoppingcart-ui:${env.BUILD_ID} ."
                }
            }
        }
        stage('zipkin-server docker image'){
            steps{
                dir('zipkin-server'){
                    sh "docker build -t zipkin-server:${env.BUILD_ID} ."
                }
            }
        }
    }
}
