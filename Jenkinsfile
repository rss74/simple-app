pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages{
        stage("Build"){
           steps{
               sh 'mvn clean package'     
           } 
        }
           stage("Upload war to nexus"){
           steps{
               nexusArtifactUploader artifacts: [
                   [
                       artifactId: 'simple-app', 
                       classifier: '', 
                       file: 'target/simple-app-3.0.0.war', 
                       type: 'war'
                    ]
                ], 
                credentialsId: '', 
                groupId: 'in.javahome', 
                nexusUrl: '172.31.11.18:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'http://65.0.109.83:8081/repository/simpleapp-release', 
                version: '3.0.0'
                  
           } 
        }  
    }
}