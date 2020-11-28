pipeline {
    agent any

    stages {
        
            stage('Compile') {
                steps {
                    dir('C:\\Users\\Flavio\\Downloads\\Downloads\\Universidad\\DiplomadoDevOpsUSACH\\Clases\\Unidad_3\\ejemplo-maven') {
                        sh 'mvn clean compile -e'
                    }
                }
            }
            stage('Test') {
                steps {
                    dir('C:\\Users\\Flavio\\Downloads\\Downloads\\Universidad\\DiplomadoDevOpsUSACH\\Clases\\Unidad_3\\ejemplo-maven') {
                        sh 'mvn clean test -e'
                    }
                }
            }
            stage('Jar') {
                steps {
                    dir('C:\\Users\\Flavio\\Downloads\\Downloads\\Universidad\\DiplomadoDevOpsUSACH\\Clases\\Unidad_3\\ejemplo-maven') {
                        sh 'mvn.cmd clean package -e'
                    }
                }
            }
			stage('Run Jar') {
                steps {
                    dir('C:\\Users\\Flavio\\Downloads\\Downloads\\Universidad\\DiplomadoDevOpsUSACH\\Clases\\Unidad_3\\ejemplo-maven') {
                        sh 'mvn spring-boot:run &'
                    }
                }
            }
			stage('Sleep') {
                steps {
                    dir('C:\\Users\\Flavio\\Downloads\\Downloads\\Universidad\\DiplomadoDevOpsUSACH\\Clases\\Unidad_3\\ejemplo-maven') {
                        sh 'sleep 30'
                    }
                }
            }
			stage('Testing_aplication') {
                steps {
                    dir('C:\\Users\\Flavio\\Downloads\\Downloads\\Universidad\\DiplomadoDevOpsUSACH\\Clases\\Unidad_3\\ejemplo-maven') {
                        sh 'curl -X GET http://localhost:8081/rest/mscovid/test?msg=testing'
                    }
                }
            }
    }
}
