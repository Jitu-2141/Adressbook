pipeline{
    tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
    agent any
    stages{
    stage("clean"){
            steps{
                sh 'mvn clean'
            }
        }
    //{
      /*  label 'sarthak12345'
    }*/
    //environment{ sart
        //PATH="C:\Users\Sarthak Sourav\Desktop\apache-maven-3.3.9\bin:$PATH"
    //}
    
        stage("checkout"){
            steps{
                git credentialsId: 'a2d1c8f2-9cb1-46eb-88de-bb8f0a3f5718', url: 'https://github.com/sart-glitch/sarthak1.git'
            }
        }
        stage("compile"){
            steps{
                sh 'mvn compile'
            }
        }
        stage("code-review"){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage("test"){
            steps{
                sh 'mvn test'
            }
        }
       
        stage("code coverage"){
            steps{
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }
        stage("package"){
            steps{
                sh 'mvn package'
            }
        }
        
        
    }
}
