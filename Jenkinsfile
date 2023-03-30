pipeline {
    agent any
 
    tools {
    jdk 'JAVA_HOME'
    maven 'MAVEN_HOME'
  }
      
    stages {
        stage('Clone'){
            steps{
                echo 'Cloning code.......'
                git 'https://github.com/Ashwinilahire/spring-boot-microservices-series.git'
            }
        }
        stage('Build'){
            steps{
                echo 'Building .......'
                sh './mvnw clean install -P buildDocker'
            }
        }
        stage('config-server docker image'){
            steps{
                dir('config-server'){
                    echo 'config-server docker image.......'
                    sh "docker build -t config-server:${env.BUILD_ID} ."
                }
            }
        }
        stage('service-registry docker image'){
            steps{
                dir('service-registry'){
                    echo 'service-registry docker image.......'
                    sh "docker build -t service-registry:${env.BUILD_ID} ."
                }
            }
        }
        stage('hystrix-dashboard docker image'){
            steps{
                dir('hystrix-dashboard'){
                    echo 'hystrix-dashboard docker image.......'
                    sh "docker build -t hystrix-dashboard:${env.BUILD_ID} ."
                }
            }
        }
        stage('catalog-service docker image'){
            steps{
                dir('catalog-service'){
                    echo 'catalog-service docker image.......'
                    sh "docker build -t catalog-service:${env.BUILD_ID} ."
                }
            }
        }
        stage('inventory-service docker image'){
            steps{
                dir('inventory-service'){
                    echo 'inventory-service docker image.......'
                   sh "docker build -t inventory-service:${env.BUILD_ID} ."
                }
            }
        }
        stage('order-service docker image'){
            steps{
                dir('order-service'){
                     echo 'order-service docker image.......'
                    sh "docker build -t order-service:${env.BUILD_ID} ."
                }
            }
        }   
        stage('shoppingcart-ui docker image'){
            steps{
                dir('shoppingcart-ui'){
                    echo 'shoppingcart-ui docker image.......'
                    sh "docker build -t shoppingcart-ui:${env.BUILD_ID} ."
                }
            }
        }
        stage('zipkin-server docker image'){
            steps{
                dir('zipkin-server'){
                    echo 'zipkin-server docker image.......'
                    sh "docker build -t zipkin-server:${env.BUILD_ID} ."
                }
            }
        }
    }
}
