pipeline{
    agent any
    environment{
        PATH = "$PATH:/opt/apache-maven-3.6.3/bin"
    }
    stages{
        stage('Get Code'){
            steps{
                git "https://github.com/inchara1998/web-app-maven.git"
        }
    }
        stage('Build'){
            steps{
                sh 'mvn clean package'
        }
        
    }
        stage('code analysis'){
            steps{
                withSonarQubeEnv('sonarqube'){
                    sh "mvn sonar:sonar"
            }
        }
    }
}   
}