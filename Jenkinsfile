pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '7fbac591-d405-4998-b65b-2ea2c5cafd2a', path: '', url: 'http://ec2-18-118-138-31.us-east-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapppipeline', 
                war: '**/java-web-project-1.0-SNAPSHOT.war'
            }
        }
    }
}
