pipeline {
    agent any

    stages {
        
            stage('Compile') {
                steps {
		    sh 'mvn clean compile -e'
                    }
                }
            stage('Test') {
                steps {
                     sh 'mvn clean test -e'
                    }
                }
            stage('Jar') {
                steps {
                    
                    sh 'mvn.cmd clean package -e'
                    }
			}
			
		stage('SonarQube analysis') {
			steps{
			withSonarQubeEnv(credentialsId: 'f225455e-ea59-40fa-8af7-08176e86507a', installationName: 'My SonarQube Server') 
				{
				sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
				}
			}
		}
			stage('Run Jar') {
                steps {
                    
                        sh 'mvn spring-boot:run &'
                    }
            
            }
			stage('Sleep') {
                steps {
                    
                        sh 'sleep 100'
                    }
                
            }
			stage('Testing_aplication') {
                steps {
                    
                        sh 'curl -X GET http://localhost:8081/rest/mscovid/test?msg=testing'
                    }
                
            }
    }
}
