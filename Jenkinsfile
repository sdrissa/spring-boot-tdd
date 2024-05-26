pipeline {
    agent any

    stages {
        stage('Github'){
            steps{
                git(
                url:'https://github.com/sdrissa/spring-boot-tdd.git',
                branch: "main",
                changelog: true,
                poll: true
                )
            }
        }
          stage('Build artifact'){
            steps{
                sh "mvn clean package -DskipTests=true"
                archive 'target/*.jar' //so that they can be downloaded later
            }
        }
    }
}