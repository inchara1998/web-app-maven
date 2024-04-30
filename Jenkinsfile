pipeline{
    agent any
    environment{
        PATH = "$PATH:/opt/apache-maven-3.6.3/bin"
    }
    stages{
        stage('Get the Code'){
            steps{
                git "https://github.com/inchara1998/web-app-maven.git"
        }
    }
        stage('Build the code'){
            steps{
                sh 'mvn clean package'
        }
        
    }
        stage('code the analysis'){
            steps{
                withSonarQubeEnv('sonarqube'){
                    sh "mvn sonar:sonar"
            }
        }
    }
        stage('Deploy the coddddddde'){
            steps{
                sshagent(['Tomcat-server']) {
                    sh 'scp -o StrictHostKeyChecking=no target/web-Maven-App.war ec2-user@3.218.255.23:/home/ec2-user/apache-tomcat-9.0.74/webapps'
}
   
}   
}
}
}
